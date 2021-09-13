<template>
  <div class="error-404 flex flex-col flex-center mobile-h-full">
    <div class="wrapper flex flex-col flex-align-center flex-center">
      <img
        class="error-img"
        alt="error-404"
        src="../static/error-404.svg"
      >
      <nuxt-link
        class="error-button has-text-centered"
        :to="localePath('/')"
      >
        {{$t('error-404')}}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'error-404',
  layout: 'default',
  props: {
    error: { type: Object, default: null }
  },
}
</script>

<style lang="scss">
.error-404 {
  @media (max-width: 1920px) {
    padding-top: 60px;
  }
  .error-button {
    text-align: center;
    font-size: 16px;
    color: azure;
    background-color: #0d324d;
    cursor: pointer;
    text-decoration: none;
    padding: 0.8rem 1.6rem;
    border: 1px solid white;
    border-radius: 5px;
    &:hover {
      color: rgb(17, 158, 200);
      border-color: rgb(17, 158, 200);
      background-color: azure;
    }
    @media (max-width: 360px) {
      width: 80%;
      font-size: 14px;
    }
    @media (min-width: 361px) {
      min-width: 200px;
      max-width: 350px;
      font-size: 14px;
    }
  }
  .error-img {
    @media (max-width: 1024px) {
      width: 100%;
    }
    @media (min-width: 1025px) and (max-width: 1600px) {
      width: 600px;
    }
    max-width: 1000px;
  }
}
</style>