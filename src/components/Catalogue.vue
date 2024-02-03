<template>
  <div class="catalog">
    <div class="catalog__title">
        Каталог товаров
    </div>
    <div class="catalog__items">
      <template v-for="item in catalogItemsList" :key="item.itemTitle">
        <ItemTypeCard :item-img-url="item.itemImgUrl" :item-title="item.itemTitle" :item-qty="item.itemQty"/>
      </template>
    </div>
  </div>
</template>

<script>
import ItemTypeCard from "@/components/ItemTypeCard";
import catalogItems from "@/assets/catalogItems";
export default {
  name: "CatalogueBod",
  components: {ItemTypeCard},
  data() {
    return {
      catalogItemsList: catalogItems
    }
  },
}
</script>

<style lang="scss" scoped>
  .catalog {
    max-width: 1110px;
    font-family: "SF UI Text", sans-serif;
    margin-top: 20px;
    padding: 0 165px;
    color: #333333;
    .catalog__title {
        font-size: 36px;
        line-height: 42.96px;
        text-shadow: 0 4px 4px #00000040;
      font-weight: bold;
    }
    .catalog__items {
      margin-top: 30px;
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
    }
  }
</style>