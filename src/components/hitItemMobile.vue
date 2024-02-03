<template>
  <div class="hit-item">
    <div class="hit-item__logo">
      <div class="hit-item__logo__img">
        <img :src="item.itemImgUrl" height="225" width="225"/>
        <img src="@/assets/youTubeIco.svg" class="logo__img__you-tube-sticker">
        <img src="@/assets/hitRuIco.svg" class="logo__img__hit-sticker">
      </div>
    </div>
    <div class="hit-item__title">
      {{item.itemTitle}}
    </div>
    <div class="hit-item__ratings">
      <RatingStars/> {{item.itemRatingQty}} отзывов
    </div>
    <div class="hit-item__price">
      <div class="hit-item__price--new">
        {{item.itemNewPrice}} ₽
      </div>
      <div v-if="item.itemOldPrice" class="hit-item__price--old">
        {{item.itemOldPrice}} ₽
      </div>
    </div>
    <div class="hit-item__in-stock">
      <div v-if="item.inStock">
          <img src="@/assets/inStockIcon.svg" >
          В наличии
      </div>
    </div>
    <div class="hit-item__buttons">
      <button class="hit-item__buttons__in-cart-button">
        В корзину
      </button>
      <div class="hit-item__buttons__other-buttons">
        <img src="@/assets/mobileComparisonIcon.svg">
        <img src="@/assets/favoriteIcon.svg" height="16" width="16">
      </div>
    </div>
    <div class="hit-item__buy-in-one">
      Купить в 1 клик
    </div>
  </div>
</template>

<script>
import RatingStars from "@/components/RatingStars";
export default {
  name: "HitItemMobile",
  components: {RatingStars},
  props: {
    item: {
      type: Object,
      default(){
        return {
          itemTitle: 'Смартфон Apple Iphone 8 64GB Gold',
          itemImgUrl: '/hitsImages/phone1.png',
          itemRating: 5,
          itemRatingQty: 10,
          itemNewPrice: '56 890',
          itemOldPrice: '56 990',
          inStock: true
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.hit-item{
  width: 345px;
  height: 532px;
  .hit-item__logo{
    margin-top: 20px;
    .hit-item__logo__img{
      width: 225px;
      height: 225px;
      position: relative;
      margin-left: 45px;
      .logo__img__fast-view{
        display: none;
        flex-direction: column;
        position: absolute;
        height: 137px;
        width: 137px;
        gap: 66px;
        bottom: 38%;
        right: 39%;
        .img__fast-view__expand-panel {
          display: flex;
          justify-content: flex-end;

        }
      }
      .logo__img__you-tube-sticker {
        position: absolute;
        bottom: 90.5%;
        left: 108%;
      }
      .logo__img__hit-sticker{
        bottom: 90%;
        right: 217px;
        position: absolute;

      }
    }
  }
  .hit-item__title {
    font-family: "SF UI Text", sans-serif;
    font-size: 14px;
    font-weight: bold;
    line-height: 20.05px;
    margin-top: 16px;
    margin-left: 5px;
  }
  .hit-item__ratings {
    display: flex;
    margin-top: 20px;
    margin-left: 5px;
    gap: 10px;
    color: #828282;
    font-size: 13px;
    line-height: 15.51px;
    font-family: "SF UI Text", sans-serif;
  }
  .hit-item__price {
    margin-top: 16px;
    font-family: "SF UI Text", sans-serif;
    display: flex;
    margin-left: 5px;
    .hit-item__price--new {
      font-size: 22px;
      font-weight: bold;
      line-height: 26.25px;
    }
    .hit-item__price--old {
      display: flex;
      align-items: flex-end;
      margin-left: 10px;
      font-size: 14px;
      color: #C4C4C4;
      text-decoration: line-through;
      line-height: 21.48px;
    }
  }
  .hit-item__in-stock {
    display: flex;
    flex-direction: column;
    color: #27AE60;
    font-family: "SF UI Text", sans-serif;
    font-size: 13px;
    line-height: 15.51px;
    margin-top: 20px;
    margin-left: 5px;
  }
  .hit-item__buttons {
    margin-top: 16.5px;
    display: flex;
    align-items: center;
    margin-left: 5px;
    gap: 21px;
    border-bottom: 1px solid #F2F2F2;
    padding-bottom: 20px;
    .hit-item__buttons__in-cart-button {
      font-family: "SF UI Text", sans-serif;
      font-size: 14px;
      line-height: 16.71px;
      width: 230px;
      height: 40px;
      background: #2D9CDB;
      border: none;
      border-radius: 4px;
      color: #FFFFFF;
    }
    .hit-item__buttons__other-buttons{
      display: flex;
      gap: 20px
    }
  }
  .hit-item__buy-in-one {
    text-align: center;
    margin-top: 15px;
    font-size: 14px;
    line-height: 16.71px;
    color: #2D9CDB;
  }
}
</style>