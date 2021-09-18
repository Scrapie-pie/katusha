<template>
  <BaseSection className="contact-us">
    <div class="contact-us__wrapper">
      <div class="contact-us__content">
        <h2 class="contact-us__title">ООО «Катюша Ай Ти»</h2>
        <div class="contact-us__info">
          <div class="contact-us__contacts">
            <BaseContact value="+7 (495) 120 11 25"/>
            <BaseContact value="mail@katusha-it.ru"/>
          </div>
          <div class="contact-us__dynamic">
            <div class="contact-us__address">
              123112, Россия, г. Москва, Пресненская набережная д. 8, стр. 1
            </div>
            <div class="contact-us__tabs">
              <div class="contact-us__tab">
                ММДЦ «Москва-Сити»
              </div>
              <div class="contact-us__tab">
                МФК «Город Столиц»
              </div>
            </div>
          </div>
        </div>
      </div>

      <YandexMaps :coords="this.coords" :placemarks="this.items" :zoom="this.zoom"></YandexMaps>
    </div>
  </BaseSection>
</template>

<script>
export default {
  name: 'SectionContactUs',
  props: {},
  data() {
    return {
      zoom: 15,
      items: [
        [55.747286, 37.539099],
      ],
      coords: [55.747286, 37.539099]
    };
  },
}
</script>

<style lang="scss">
.contact-us {
  &__wrapper {
    display: grid;
    grid-template-columns: 340px auto;
    height: 500px;
    gap: 30px;
  }
  &__content {
    //@include flex-container(column, 55px);
  }
  &__title {
    margin-bottom: 55px;
  }
  &__info {
    width: 100%;
    max-width: 315px;
    @include flex-container(column, 60px);
  }
  &__contacts {
    //margin: 55px 0 60px;
    @include flex-container(column, 20px);
    font-size: 28px;
    color: get-variable(color, blue);
    padding-top: 25px;
    border-top: 1px solid get-variable(color, grey);
  }
  &__dynamic {
    @include flex-container(column, 25px);
    color: get-variable(color, grey_dark);
  }
  &__address {
    font-size: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid get-variable(color, grey);
    font-weight: 300;
  }
  &__tabs {
    font-size: 14px;
    font-weight: 300;
    //display: grid;
    //grid-template-columns: repeat(auto-fit, minmax(135px, 1fr));
    //gap: 15px;
    @include flex-container(row, 15px);
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;

    // & > * {
    //   &:first-child {
    //     justify-self: flex-start;
    //   }
    //   &:last-child {
    //     justify-self: flex-end;
    //   }
    // }
  }

}
</style>
