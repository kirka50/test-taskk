<template>
  <div class="item-card">
    <div class="item-card__image">
      <img :src="itemImgUrl" :alt="itemTitle" width="155" height="155">
    </div>
    <div class="item-card__title">
      {{itemTitle}}
    </div>
    <div class="item-card__item-qty">
      {{itemQty}} товара
    </div>
  </div>
</template>

<script>
export default {
  name: "ItemTypeCard",
  props: {
    itemImgUrl: {
      type: String,
      default: 'itemImages/pcImage.png'
    },
    itemTitle: {
      type: String,
      default: 'Компьютеры'
    },
    itemQty: {
      type: String,
      default: '393'
    },

  },
}
</script>

<style lang="scss" scoped>
  .item-card {
    text-align: center;
    font-family: "SF UI Text", sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 255px;
    height: 299px;
    color: #333333;
    &:hover {
      border-radius: 1px;
      box-shadow: 0 0 15px #0000000D;
      cursor: pointer;
      .item-card__title{
        color: #2D9CDB;
      }
    }
    .item-card__image {
      margin-top: 25px;
      img {
      }
    }
    .item-card__title {
      margin-top: 15px;
      font-size: 18px;
      line-height: 25.78px;
      height: 50px;
      width: 215px;
    }
    .item-card__item-qty {
      font-family: "SF UI Text light", sans-serif;
      margin-top: 10px;
      font-size: 18px;
      line-height: 25.31px;
    }
  }
</style>