<template>
  <div>
    <section class="services">
      <div class="services__container">
        <div class="services__block">
          <p class="services__text">Услуг</p>
        </div>
        <div class="services__flex">
          <div class="diagram diagram__decoration">
            <p class="diagram__text">Ручное бродинование</p>
          </div>
          <p class="diagram__number">11</p>
        </div>
        <div class="services__flex">
          <div class="diagram diagram--color diagram__line"></div>
          <div class="diagram--position">
            <p class="diagram__text">Пакетные туры</p>
          </div>
          <p class="diagram__number diagram__number--position">3</p>
        </div>
        <div class="services__flex">
          <div class="diagram diagram--color diagram--width"></div>
          <div class="diagram--position">
            <p class="diagram__text">Отели</p>
          </div>
          <p class="diagram__number diagram__number--position">1</p>
        </div>
        <div class="services__line"></div>
        <div class="services__flex services__total">
          <div><p class="total__text">Всего</p></div>
          <div><p class="total__number diagram__number--position">15</p></div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "presentation"
};
</script>

<style lang="scss" scoped>
.services__container {
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;

  position: relative;
  padding-left: 19px;
  padding-right: 53px;

  padding-bottom: 20px;

  font-family: "Arial", sans-serif;

  @media screen and (min-width: 480px) {
    padding-left: 151px;
  }
}

.services__block {
  display: flex;
  justify-content: flex-end;

  margin-bottom: 23px;
}

.services__text {
  font-size: 13px;
  line-height: 1.15;

  margin: 0;

  color: #333333;
}

.services__flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.diagram {
  width: 219px;
  height: 24px;

  margin-bottom: 2px;

  background-color: #b1e19b;
  border-radius: 0px 3px 3px 0px;
}

.diagram__decoration::before {
  content: "";
  position: absolute;
  width: 91%;
  height: 0px;

  top: 23px;
  right: 4%;

  border: 1px solid #dadada;

  @media screen and (min-width: 480px) {
    width: 65%;
  }

  @media screen and (min-width: 720px) {
    width: 75%;
  }
}

.diagram__decoration::after {
  content: "";
  position: absolute;
  width: 91%;
  height: 0px;

  top: 125px;
  right: 4%;

  border: 1px solid #dadada;

  @media screen and (min-width: 480px) {
    width: 65%;
  }

  @media screen and (min-width: 720px) {
    width: 75%;
  }
}

.diagram--color {
  position: relative;

  width: 54px;
  height: 24px;

  background: #ace2f8;
  border-radius: 0px 3px 3px 0px;
}

.diagram__text {
  margin: 0;
  padding-left: 6px;

  font-size: 12px;
  line-height: 2;

  color: #333333;

  @media screen and (min-width: 480px) {
    font-size: 13px;
  }
}

.diagram__number {
  margin: 0;
  padding-right: 7px;

  font-size: 13px;
  line-height: 1.15;
  font-weight: 700;

  color: #333333;
}

.diagram--position {
  position: absolute;
}

.diagram__line::before {
  content: "";
  position: absolute;
  width: 76px;
  height: 0px;
  left: -37px;
  top: 11px;

  border: 1px solid rgba(51, 51, 51, 0.2);
  transform: rotate(90deg);
}

.diagram--width {
  width: 36px;
}

.diagram__number--position {
  padding-right: 9px;
}

.services__total {
  margin-top: 24px;
}

.total__text {
  font-weight: 700;
  font-size: 16px;
  line-height: 1.62;

  color: #333333;
}

.total__number {
  font-weight: 700;
  font-size: 16px;
  line-height: 0, 94;

  color: #333333;
}
</style>
