<template>
  <div class="mobile-page">
    <div class="mobile-page__logo">
      <div class="mobile-page__logo__img">
        <img src="@/assets/car.svg">
      </div>
      <div class="mobile-page__logo__text">
        <div class="text__title">
          Доставка по России
        </div>
        <div class="text__body">
          Осуществляется транспортными компаниями или Почтой России
        </div>
      </div>
    </div>
    <div class="mobile-page__popular-cat">
      <div class="mobile-page__popular-cat__title">
        Популярные категории
      </div>
      <div class="mobile-page__popular-cat__categories">
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/pcImage.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Компьютеры
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              393
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/clothingImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Одежда
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              245
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/electricImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Электроника
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              456
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/autoImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Автотовары
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              128
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/sportImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Спорт и отдых
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              197
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/childImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Детские товары
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              86
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/fishImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Туризм и рыбалка
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              92
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
        <div class="popular-cat__categories__category" style="border: none">
          <div class="categories__category__title">
            <div class="category__title__img">
              <img src="/itemImages/toolsImg.png" height="34" width="34">
            </div>
            <div class="category__title__text">
              Инструменты
            </div>
          </div>
          <div class="categories__category__button">
            <div class="category__button__qty">
              104
            </div>
            <div class="category__button__img">
              <img src="@/assets/arrow.svg">
            </div>
          </div>
        </div>
      </div>
      <div class="mobile-page__popular-cat__more-button">
        <button>
          Показать ещё <img src="@/assets/downIcon.svg">
        </button>
      </div>
    </div>
    <div class="mobile-page__hits">
      <div class="mobile-page__hits__upper">
        <div class="hits__upper__title">
          Хиты продаж
        </div>
        <div class="hits__upper__buttons">
          <div class="buttons__slider-button--left">
            <img src="@/assets/sliderButtton.svg" @click="pervItem">
          </div>
          <div class="buttons__slider-button--right">
            <img src="@/assets/sliderButtton.svg" @click="nextItem">
          </div>
        </div>
      </div>
      <div class="mobile-page__hits__body">
        <HitItemMobile :item="hitItems[selectedItem]"/>
      </div>
    </div>
  </div>
</template>

<script>
import HitItemMobile from "@/components/hitItemMobile";
import hitItems from "@/assets/hitItems";
export default {
  name: "MobilePage",
  components: {HitItemMobile},
  data() {
    return {
      hitItems: hitItems,
      selectedItem: 1,
    }
  },
  methods: {
    nextItem() {
      const itemsQtty = this.hitItems.length
      if (this.selectedItem == itemsQtty-1) {
        this.selectedItem = 0
      } else {
        this.selectedItem += 1
      }
    },
    pervItem() {
      const itemsQtty = this.hitItems.length
      if (this.selectedItem == 0) {
        this.selectedItem = itemsQtty-1
      } else {
        this.selectedItem -= 1
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .mobile-page {
    padding: 30px 15px 45px 15px;
    display: flex;
    flex-direction: column;
    overflow-y:scroll ;
    .mobile-page__logo {
      display: flex;
      gap: 20px;

      .mobile-page__logo__img {
        display: flex;
        align-items: center;
      }
      .mobile-page__logo__text{
        font-family: "SF UI Text", sans-serif;
        color: #333333;

        .text__title {
          font-size: 16px;
          line-height: 18.75px;
          font-weight: bold;
        }
        .text__body {
          margin-top: 5px;
          font-size: 14px;
          line-height: 19.69px;
        }
      }
    }
    .mobile-page__popular-cat {
      margin-top: 42.82px;
      .mobile-page__popular-cat__title {
        font-family: "SF UI Text", sans-serif;
        color: #333333;
        font-size: 22px;
      }
      .mobile-page__popular-cat__categories{
        margin-top: 18px;
        font-family: "SF UI Text", sans-serif;
        .popular-cat__categories__category {
          display: flex;
          height: 60px;
          max-width: 375px;
          align-items: center;
          justify-content: space-between;
          margin-bottom: -1px;
          border-bottom: 1px solid #EBF8FF;
          .categories__category__title{
            display: flex;
            align-items: center;
            gap: 15px;
            font-size: 14px;
            line-height: 20.05px;
            .category__title__img {
              display: flex;
              align-items: center;
            }
          }
          .categories__category__button {
            display: flex;
            gap: 15px;
            .category__button__qty {
              font-size: 14px;
              line-height: 20.05px;
              text-align: right;
              color: #A0A0A0;
            }
          }
        }
      }
      .mobile-page__popular-cat__more-button {
        display: flex;
        justify-content: center;
        margin-top: 15px;
        button {
          background: #FFFFFF;
          border: 1px solid #2D9CDB;
          border-radius: 5px;
          width: 159px;
          height: 40px;
          color: #2D9CDB;
          font-family: "SF UI Text", sans-serif;
          font-size: 14px;
          line-height: 16.71px;
          display: flex;
          align-items: center;
          justify-content: center;
          gap: 9px;
        }
      }
    }
    .mobile-page__hits {
      margin-top: 34px;
      font-family: "SF UI Text", sans-serif;
      .mobile-page__hits__upper {
        display: flex;
        justify-content: space-between;
        .hits__upper__title {
          font-size: 22px;
          font-weight: bold;
          line-height: 26.25px;
        }
        .hits__upper__buttons {
          display: flex;
          gap: 8px;
          max-height: 30px;
          .buttons__slider-button--right {
            img {
              transform: rotate(180deg);
            }
          }
        }
      }
      .mobile-page__hits__body {
        margin: 15px;
        display: flex;
        justify-content: center;

      }
    }
  }
</style>