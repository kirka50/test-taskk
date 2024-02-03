<template>
  <div class="logos">
    <div class="logos__logo">
      <div class="logo__img">
        <img src="@/assets/car.svg" alt="машина"/>
      </div>
      <div class="logo__text">
        <div class="logo__text__title">
          Доставка по России
        </div>
        <div class="logo__text__body">
          Осуществляется транспортными компаниями или Почтой России
        </div>
      </div>
    </div>
    <div class="logos__logo">
      <div class="logo__img">
        <img src="@/assets/wallet.svg" alt="машина"/>
      </div>
      <div class="logo__text">
        <div class="logo__text__title">
          On-line оплата на сайте
        </div>
        <div class="logo__text__body">
          Оплата производится банковской картой&#160; и электронными деньгами
        </div>
      </div>
    </div>
    <div class="logos__logo">
      <div class="logo__img">
        <img src="@/assets/coupon.svg" alt="машина"/>
      </div>
      <div class="logo__text">
        <div class="logo__text__title">
          Система скидок
        </div>
        <div class="logo__text__body">
          Накопительные скидки и бонусная программа для наших клиентов
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UpperLogos"
}
</script>

<style lang="scss" scoped>
  .logos{
    max-width: 1440px;
    display: flex;
    justify-content: space-around;
    gap: 30px;
    padding: 57px 165px;
    .logos__logo{
      max-width: 350px;
      max-height: 63px;
      display: flex;
      gap: 20px;
      .logo__img {
        display: flex;
        justify-items: center;
      }
      .logo__text {
        display: flex;
        gap: 5px;
        color: #333333;
        flex-direction: column;
        .logo__text__title {
          font-family: "SF UI Text", sans-serif;
          font-size: 16px;
          font-weight: bold;
          line-height: 18.75px;
        }
        .logo__text__body {
          font-family: "SF UI Text", sans-serif;
          font-size: 14px;
          line-height: 19.69px;
        }
      }
    }
  }
</style>