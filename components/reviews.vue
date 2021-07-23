<template>
  <div>
    <section class="reviews">
      <div class="reviews__container">
        <div class="reviews__flex">
          <div class="reviews__block">
            <p class="reviews__last">Последние отзывы</p>
            <a class="reviews__all">Все отзывы</a>
          </div>
          <div class="reviews__block">
            <svg width="12px" height="11px" class="reviews__icon">
              <use href="~static/inlineSprite.svg#src-1"></use>
            </svg>
            <p class="reviews__number reviews__number--position">131</p>
            <svg width="13px" height="13px" class="reviews__icon">
              <use href="~static/inlineSprite.svg#src-2"></use>
            </svg>
            <p class="reviews__number">14</p>
          </div>
        </div>
        <div class="reviews__last non" v-if="comment.length === 0">
          Оставьте отзыв
        </div>
        <div class="comments" v-if="comment.length > 0">
          <ul
            class="list comments__list"
            v-for="item in comment"
            :key="item.id"
          >
            <li class="comments__item">
              <div class="reviews__block">
                <p class="comments__text">{{ item.name }}</p>
                <p class="comments__date">{{ date }}</p>
              </div>
              <div class="arrow-div">
                <p>{{ item.comment }}</p>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </section>
    <section class="form">
      <form>
        <label for="comment"></label>
        <textarea
          v-model="submit"
          type="text"
          class="form__input"
          id="comment"
          @keyup.ctrl.enter.exact="addComment(submit)"
          name="comment"
        ></textarea>
        <div class="form__flex">
          <button @click="addComment(submit)" type="button" class="form__btn">
            Написать консультанту
          </button>
        </div>
      </form>
    </section>
  </div>
</template>

<script>
export default {
  name: "presentation",
  data() {
    return {
      idComment: 0,
      submit: "",
      comment: [],
      name: ["Самуил", "Лилия Семёновна", "Иван", "Андрей", "Алексей"]
    };
  },

  computed: {
    date() {
      return new Date().toLocaleString().slice(0, 10);
    }
  },

  methods: {
    addComment(item) {
      const reviews = {
        id: (this.idComment += 1),
        name: this.random(),
        comment: item
      };
      this.comment.push(reviews);
      this.submit = "";
    },
    random() {
      return this.name[Math.floor(Math.random() * this.name.length)];
    }
  }
};
</script>

<style lang="scss" scoped>
.reviews__container {
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;

  padding-right: 19px;
  padding-left: 19px;
  padding-bottom: 22px;

  font-family: "Arial", sans-serif;
}

.reviews__flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.reviews__block {
  display: flex;
  align-items: center;
}

.reviews__last {
  margin: 0;

  margin-right: 16px;

  font-weight: 700;
  font-size: 14px;
  line-height: 1;

  color: #333333;

  @media screen and (min-width: 480px) {
    font-size: 16px;
  }
}

.reviews__all {
  margin: 0;

  font-size: 14px;
  line-height: 1.14;

  text-decoration-line: underline;

  color: #005da1;
}

.reviews__icon {
  margin-right: 2px;
}

.reviews__number {
  margin: 0;

  font-size: 12px;
  line-height: 1.17;

  color: #333333;
}

.reviews__number--position {
  margin-right: 16px;
}

.arrow-div {
  margin-top: 12px;
  padding: 20px 17px 12px 20px;
  position: relative;

  min-height: 55px;

  word-break: break-word;

  background: #f2fbff;
  border: 1px solid #c4cbcf;

  box-shadow: 0px 4px 10px rgba(128, 128, 128, 0.1);
}

.arrow-div:before {
  content: "";
  position: absolute;
  left: 8px;
  bottom: 100%;
  border-style: solid;
  border-width: 15px 15.5px 0 15.5px;
  border-color: transparent transparent transparent #f2fbff;
}

.comments {
  padding-top: 11px;
  padding-bottom: 22px;
}

.comments__list {
  padding: 0;
}

.comments__text {
  margin-bottom: 0;
  margin-right: 16px;

  font-weight: 700;
  font-size: 14px;
  line-height: 1.36;

  color: #333333;
}

.comments__date {
  margin-bottom: 0;

  font-size: 11px;
  line-height: 1.72;

  color: #808080;
}

.comments__item {
  margin-bottom: 16px;
}

.form {
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;

  padding-top: 28px;
  padding-left: 21px;
  padding-right: 21px;
  padding-bottom: 34px;

  background-color: #f2f2f2;
}

.form__input {
  width: 100%;
  min-height: 63px;
  padding: 10px;

  background: #ffffff;
  border: 1px solid #000000;
  border-radius: 1px;
  outline-color: #000000;
}

.form__flex {
  display: flex;
  justify-content: center;

  margin-top: 23px;
}

.form__btn {
  width: 281px;
  height: 43px;

  background: #fdd639;
  border-radius: 23px;

  font-family: "PT Sans", sans-serif;
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 1.31;

  color: #333333;
}

.non {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

.form__output {
  width: 100%;
}
</style>
