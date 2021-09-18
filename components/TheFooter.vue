<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__wrapper">
        <div class="footer__top">
          <div class="achievments">
            <div class="achievments__item">
              <img src="~/../src/images/badge01.png" alt="image"/>
              <span>ООО КАТЮША Ай Ти член Ассоциации разработчиков программных продуктов «Отечественный софт»</span>
            </div>
            <div class="achievments__item">
              <img src="~/../src/images/badge02.png" alt="image"/>
              <span>Исследования осуществляются ООО КАТЮША Ай Ти при грантовой поддержке Фонда «Сколково»</span>
            </div>
            <div class="achievments__item">
              <img src="~/../src/images/badge03.png" alt="image"/>
              <span>ООО КАТЮША Ай Ти член Российского союза промышленников и предпринимателей</span>
            </div>
          </div>
          <BaseButton>Скачать презентацию</BaseButton>
        </div>
        <div class="footer__bottom">
          <span>© 2021 КАТЮША Ай Ти. Все права защищены</span>
          <div class="footer__contacts">
            <BaseContact value="+7 (495) 120 11 25"/>
            <BaseContact value="mail@katusha-it.ru"/>
          </div>
          <span>Политика конфиденциальности</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'TheFooter',
  data() {
    return {
      badges: {
        //img: '~/src/images/badge01.png'
      }
    }
  }
}
</script>

<style lang="scss">
.footer {
  &__wrapper {
    @include flex-container(column, 40px);
  }

  &__top {
    @include flex-container(row, 30px);
    justify-content: space-between;
    align-items: center;
  }

  &__bottom {
    display: grid;
    grid-template-columns: 1fr 310px 1fr;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid get-variable(color, grey);
    padding: 25px 0;
    font-size: 14px;

    & > * {
      &:first-child {
        justify-self: flex-start;
      }
      &:last-child {
        justify-self: flex-end;
      }
    }
  }

  &__contacts {
    @include flex-container(row, 15px);
    align-items: center;
    justify-content: space-between;
  }
  .contact {
    .icon {
      color: get-variable(color, light);
    }
  }


}

.achievments {
  display: grid; // test flex
  grid-template-columns: repeat(auto-fit, minmax(auto, 325px));
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  width: 100%;

  &__item {
    @include flex-container(column, 10px);
    align-items: flex-start;
    font-size: 14px;
    color: get-variable(color, grey_dark);
  }
}
</style>
