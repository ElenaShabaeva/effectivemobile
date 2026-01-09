<template>
  <div class="listing container">
    <div class="listing__container">
      <div class="listing__top">
        <h1 class="listing__title">Афиша</h1>
        <div class="listing__search">
          <my-input
            :label="'Название фильма'"
            :required="true"
            :inputName="'MovieName'"
            :placeholder="'Название фильма'"
          />
          <my-button-s type="button" :filled="true" class="listing__btn" aria-label="Поиск">
            <SvgSearch/>
          </my-button-s>
        </div>
      </div>
      <ul class="listing__movies">
        <MovieCard class="listing__movie"/>
        <MovieCard class="listing__movie"/>
        <MovieCard class="listing__movie"/>
        <MovieCard class="listing__movie"/>
        <MovieCard class="listing__movie"/>
        <MovieCard class="listing__movie"/>
      </ul>
    </div>
  </div>
</template>

<script setup>
import SvgSearch from "../assets/icons/SvgSearch.vue";
import MovieCard from "./MovieCard.vue";
</script>

<style lang="less">
.listing {
  &__container {
    .flex(flex, 60px);
  }

  &__top {
    display: grid;
    grid-template-columns: 1fr 2fr;
    align-items: center;
    column-gap: 36px;

    @media @768 {
      .flex(flex, 30px)
    }
  }

  &__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 1.33;
  }

  &__search {
    position: relative;
    width: 100%;
  }

  &__btn{
    position: absolute;
    top: 4px;
    right: 4px;
  }

  &__movies{
    display: flex;
    column-gap: 60px;
    row-gap: 64px;
    flex-wrap: wrap;

    @media @1440{
      column-gap: 40px;
    }

    @media @1024{
      column-gap: 20px;
    }

    @media @768{
      column-gap: 32px;
    }

    @media @576{
      justify-content: center;
    }
  }

  &__movie{
    width: calc(25% - 45px);
    // min-width: 280px;

    @media @1440{
      width: calc(25% - 30px);
    }
    
    @media @1024{
      width: calc(33.333% - 13.333px);
    }

    @media @768{
      width: calc(50% - 16px);
    }

    @media @576{
      max-width: 300px;
      width: 100%;
    }
  }
}
</style>
