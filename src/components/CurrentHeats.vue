<template>
  <div class="current-heats">
    <div class="current-heats__upper">
      <div class="current-heats__upper__title">
        Хиты продаж
      </div>
      <div class="current-heats__upper__slider-button">
        <div class="slider-button--left">
          <img src="@/assets/sliderButtton.svg" @click="perveriosItem">
        </div>
        <div class="slider-button-right">
          <img src="@/assets/sliderButtton.svg" @click="nextItem">
        </div>
      </div>
    </div>
    <div class="current-heats__items">
        <HitItem v-for="item in hitsItems" :key="item" :item="item"/>
    </div>
  </div>
</template>

<script>
import HitItem from "@/components/hitItem";
import hitItems from "@/assets/hitItems";
export default {
  name: "CurrentHeats",
  components: {HitItem},
  data() {
    return {
      hitsItems: hitItems
    }
  },
  methods: {
    nextItem() {
      const x = this.hitsItems.pop()
      this.hitsItems.unshift(x)
    },
    perveriosItem() {
      const x = this.hitsItems.shift()
      this.hitsItems.push(x)
    }
  }

}
</script>

<style lang="scss" scoped>
  .current-heats {
    font-family: "SF UI Text", sans-serif;
    margin: 65px 165px 0 165px;
    .current-heats__upper {
      display: flex;
      align-items: flex-end;
      justify-content: space-between;
      .current-heats__upper__title {
        color: #333333;
        font-size: 36px;
        line-height: 42.19px;
      }
      .current-heats__upper__slider-button {
        display: flex;
        gap: 8px;
        img {
          cursor: pointer;
        }
        .slider-button-right {
          img {
            transform: rotate(180deg);
          }
        }
      }
    }
    .current-heats__items {
      margin-top: 34px;
      display: flex;
      gap: 30px;
    }
  }
</style>