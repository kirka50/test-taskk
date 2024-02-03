<template>
  <div class="hit-item">
    <div class="hit-item__logo">
      <div class="hit-item__logo__img">
        <img :src="item.itemImgUrl" height="215" width="215"/>
        <div class="logo__img__fast-view">
          <div class="img__fast-view__magnifier-ico">
            <img src="@/assets/magify_icon.svg">
          </div>
          <div class="img__fast-view__expand-panel">
            <img src="@/assets/expandPanel.svg">
          </div>
        </div>
          <img src="@/assets/hit.svg" class="logo__img__hit-sticker">
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
        В наличии
      </div>
    </div>
    <div class="hit-item__buttons">
      <button class="hit-item__buttons__in-cart-button">
        В корзину
      </button>
      <div class="hit-item__buttons__other-buttons">
        <img src="@/assets/comparisonIcon.svg">
        <img src="@/assets/favoriteIcon.svg">
      </div>
    </div>
  </div>
</template>

<script>
import RatingStars from "@/components/RatingStars";
export default {
  name: "HitItem",
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
          itemOldPrice: '',
          inStock: true
        }
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .hit-item{
    width: 255px;
    height: 486px;
    padding: 0 20px 0 20px;

    &:hover {
      outline: 1px solid #F4F4F4;
      border-radius: 5px;
      box-shadow: 0 0 15px #0000000D;
      .hit-item__logo {
        .hit-item__logo__img {
          .logo__img__fast-view {
            display: flex;
          }
        }
      }
    }
    .hit-item__logo{
      margin-top: 20px;
      .hit-item__logo__img{
        width: 215px;
        height: 215px;
        position: relative;
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
        .logo__img__hit-sticker{
          bottom: 90.5%;
          left: 80%;
          position: absolute;
          
        }
      }
    }

    .hit-item__title {
      width: 215px;
      font-family: "SF UI Text", sans-serif;
      font-size: 14px;
      font-weight: bold;
      line-height: 20.05px;
      margin-top: 19px;
    }
    .hit-item__ratings {
      display: flex;
      margin-top: 20px;
      gap: 10px;
      color: #828282;
      font-size: 13px;
      line-height: 15.51px;
      font-family: "SF UI Text", sans-serif;
    }
    .hit-item__price {
      margin-top: 18px;
      font-family: "SF UI Text", sans-serif;
      display: flex;
      .hit-item__price--new {
        font-size: 18px;
        font-weight: bold;
      }
      .hit-item__price--old {
        display: flex;
        align-items: flex-end;
        margin-left: 13px;
        font-size: 13px;
        color: #C4C4C4;
        text-decoration: line-through;
      }
    }
    .hit-item__in-stock {
      color: #27AE60;
      font-family: "SF UI Text", sans-serif;
      font-size: 13px;
      line-height: 15.51px;
      margin-top: 20px;
    }
    .hit-item__buttons {
      margin-top: 20px;
      display: flex;
      gap: 37px;
      align-items: center;
      .hit-item__buttons__in-cart-button {
        font-family: "SF UI Text", sans-serif;
        font-size: 14px;
        line-height: 16.71px;
        width: 120px;
        height: 35px;
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
  }
</style>