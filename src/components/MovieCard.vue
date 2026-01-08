<template>
  <li class="movie">
    <img src="/1.png" alt="" />
    <div class="movie__info">
      <span class="movie__name">Уикенд с батей (16+)</span>
      <span class="movie__text">Фильм</span>
    </div>
    <my-button type="button" :filled="true">Подробнее</my-button>
  </li>
</template>

<style lang="less">
.movie {
  .flex(inline-flex, 16px);

  &__info {
    .flex(flex, 4px);
  }

  &__name {
    font-weight: 600;
    font-size: 20px;
    line-height: 1.2;
  }

  &__text {
    color: @gray-3;
    font-family: @font;
    font-size: 14px;
  }
}
</style>
