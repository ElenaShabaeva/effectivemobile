<template>
  <div class="info">
    <div class="info__container container">
      <div class="info__wrapper">
        <my-button-s class="info__close" :filled="true">
          <SvgClose />
        </my-button-s>
        <div class="info__top">
          <p>Уикенд с батей Уикенд с батей</p>
          <span class="info__score">8,8</span>
        </div>
        <div class="info__description">
          <span class="info__subtitle">Описание фильма</span>
          <p>
            Себастьян планирует провести уикенд со своей очаровательной невестой
            Элли и ее семьей в их роскошном фамильном поместье, где есть
            собственное поле для гольфа, шикарная яхта и даже ручной
            павлинСебастьян планирует провести уикенд со своей очаровательной
            невестой Элли и ее семьей в их роскошном фамильном поместье, где
            есть собственное поле для гольфа, шикарная яхта и даже ручной павлин
          </p>
        </div>
        <div class="info__tags">
          <div class="info__tag">
            <span class="info__tag-name">Год</span>
            <span class="info__tag-text">2025</span>
          </div>
          <div class="info__tag">
            <span class="info__tag-name">Страна</span>
            <span class="info__tag-text">США</span>
          </div>
          <div class="info__tag">
            <span class="info__tag-name">Режиссер</span>
            <span class="info__tag-text">Уилл Кэнон</span>
          </div>
          <div class="info__tag">
            <span class="info__tag-name">Актеры</span>
            <span class="info__tag-text"
              >Скотт Мехловиц, Винс Айзенсон, Рон Фаллика, Захари Голингер, Джей
              Девон Джонсон, Крэйг Колкенбек, Элли Маккаллок, Флеминг Мур,
              Италиа Риччи, Терренс Розмор</span
            >
          </div>
          <div class="info__tag">
            <span class="info__tag-name">Длительность</span>
            <span class="info__tag-text">160 мин</span>
          </div>
          <div class="info__tag">
            <span class="info__tag-name">Возрастное ограничение</span>
            <span class="info__tag-text">16+</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import SvgClose from "../assets/icons/SvgClose.vue";
</script>

<style lang="less">
.info {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  padding-top: 80px;
  width: 100%;
  height: 100%;
  background-color: fade(@dark, 70%);
  overflow-y: auto;

  &__wrapper {
    .flex(flex, 24px);
    padding: 30px 20px 50px 20px;
    background-color: @light;
    border: 3px solid @purple;
    border-radius: 8px;

    @media @768{
      padding: 15px 10px 25px 10px;
    }
  }

  &__close {
    margin-left: auto;
    flex-shrink: 0;
    margin-bottom: 20px;
  }

  &__top {
    display: grid;
    grid-template-columns: 1fr auto;
    column-gap: 20px;
    align-self: self-start;

    font-weight: 700;
    font-size: 24px;
    line-height: 1.33;

    p {
      margin-block: 0;
    }
  }

  &__score {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 5px 10px;
    background-color: @gray-1;
    color: @gray-3;
    border: 1px solid @gray-2;
    border-radius: 4px;
    font-size: 14px;
    font-weight: 500;
    line-height: 1.25;
  }

  &__description {
    .flex(flex, 10px);
  }

  &__subtitle {
    font-weight: 500;
  }

  &__tags {
    .flex(flex, 14px);
  }

  &__tag {
    display: grid;
    grid-template-columns: 120px 1fr;
    column-gap: 12px;
    color: @gray-3;
    font-size: 14px;
  }

  &__tag-text {
    max-width: 550px;
    white-space: normal;
  }
}
</style>
