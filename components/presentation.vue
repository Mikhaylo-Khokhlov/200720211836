<template>
  <div>
    <section class="presentation">
      <div class="presentation__container">
        <h1 class="presentation__title">Вероника Ростова</h1>
        <p class="presentation__subtitle">Менеджер по продажам</p>
        <div class="presentation__block">
          <p class="presentation__description">
            Подберу для вас самые лучшие предложения. Мои услуги абсолютно
            бесплатны
          </p>
        </div>
        <v-avatar size="124" class="presentation__avatar">
          <img src="~/static/avatar.jpg" alt="John" />
        </v-avatar>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "home"
};
</script>

<style lang="scss" scoped>
.presentation {
  font-family: "Arial", sans-serif;
  font-weight: 400;
  background-color: #fff;
}

.presentation__container {
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;

  position: relative;

  padding-top: 21px;
  padding-right: 19px;
  padding-left: 106px;
  padding-bottom: 13px;
}

.presentation__title {
  font-size: 16px;
  line-height: 1.25;

  padding-left: 45px;
  margin-bottom: 2px;

  color: #333333;
}

.presentation__subtitle {
  font-size: 12px;
  line-height: 1.67;

  padding-left: 45px;
  margin-bottom: 5px;

  color: #808080;
}

.presentation__block {
  padding-left: 45px;
  padding-right: 14px;
  padding-top: 10px;
  padding-bottom: 10px;

  background: #fffbc8;
  border: 1px solid #dadada;
  border-radius: 5px;
}

.presentation__description {
  margin: 0;

  font-size: 10px;
  line-height: 1.43;

  color: #333333;

  @media screen and (min-width: 480px) {
    font-size: 13px;
  }
}

.presentation__avatar {
  position: absolute;
  left: 17px;
  top: 14px;

  background: #c4c4c4;
}
</style>
