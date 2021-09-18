<template>
  <header class="header">
    <div class="container">
      <div class="header__wrapper">
        <Icon icon="logo"/>
        <nav class="header__nav">
          <div class="header__ref">
            <Icon icon="eco"/>
            Экосистема
          </div>
          <div class="header__ref">
            <Icon icon="tech"/>
            Линейка “Катюша”
          </div>
          <div class="header__ref">
            <Icon icon="monitor"/>
            Программное обеспечение
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
  props: {
    //msg: String
  }
}
</script>

<style lang="scss">
.header {
  background-color: get-variable(color, white);
  box-shadow: 0px 0px 10px 0px rgb(0 0 0 / 8%);
  z-index: 10;
  //margin-bottom: 60px;

  &__wrapper {
    @include flex-container(row, 30px);
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
  }

  &__nav {
    @include flex-container(row, 40px);
  }

  &__ref {
    @include flex-container(row, 10px);
    align-items: center;
    color: get-variable(color, grey_dark);
    .icon {
      color: get-variable(color, black);
    }
  }
}
</style>
