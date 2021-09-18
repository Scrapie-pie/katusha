<template>
  <BaseSection className="skills">
    <div class="skills__wrapper">
      <div class="skills__item">
        <h2>Биометрическое распознавание лица</h2>
        <div class="skills__content">
          <img class="skills__image" src="~/../src/images/skill01.png" alt="image"/>
          <div class="skills__info">
            <h3 class="skills__subtitle">
              Авторизация на принтерах и МФУ с помощью машинного зрения
            </h3>
            <div class="skills__description">
              aasdad
            </div>
            <div class="skills__actions">
              <BaseButton>Смотреть видео</BaseButton>
            </div>
          </div>
        </div>

      </div>
      <div class="skills__item">

      </div>
      <div class="skills__item">

      </div>
    </div>
  </BaseSection>
</template>

<script>
export default {
  name: 'SectionSkills'
}

</script>

<style lang="scss">
.skills {
  $skills: &;

  &__wrapper {

  }
  &__item {

  }
  &__content {
    display: grid;
    grid-template-columns: minmax(auto, 490px) minmax(auto, 910px);
    //align-items: center;
    justify-content: space-between;
    gap: 30px;
  }
  &__info {
    height: 100%;
    @include flex-container(column)
  }
  &__subtitle + &__description {
    padding-top: 60px;
    border-top: 1px solid get-variable(color, grey);
  }
  &__description {
    height: 100%;
    padding-bottom: 20px;
  }

  &__image {
    border-radius: 10px;
  }
}
</style>
