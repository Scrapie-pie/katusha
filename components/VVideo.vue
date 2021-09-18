<template>
    <div class="v-video" @click="" :class="this.classInit">
      <div class="v-video__cover">
        <div class="v-video__caption">
          <div class="v-video__cover-caption-title">
            Глеб Кащеев Директор по развитию
          </div>
          <div class="v-video__cover-caption-text">
            на Sinergy Digital форуме
          </div>
        </div>
        <VPlay class="v-video__play"></VPlay>
      </div>

      <iframe class="v-video__broadcaster" width="560" height="315" frameborder="0" allowfullscreen :src="this.srcInit"></iframe>
    </div>
</template>

<script>

export default {
    name: "VVideo",
    components: {},
    data:() => ({
        url: "https://www.youtube.com/embed/JwpFvFpbOGc" + "?" + "autoplay=1",

    }),
    props: {
        startVideo: { type: Boolean, default: false },
    },
    computed: {
        //srcInit()   { return this.startVideo ? this.url : null },
        srcInit()   { return this.url },
        //classInit() { return this.startVideo ? "start-video" : null },
        classInit() { return true },
    }
}
</script>

<style lang="scss">
    // .v-video {
    //     position: relative;
    //     width: 100%;
    //     height: 100%;
    //     border-radius: 20px;
    //     overflow: hidden;
    //
    //     &__cover {
    //         // background: url(/upload/img/video-preview-01.jpg) no-repeat center/cover;
    //         //background: black;
    //         display: grid;
    //         grid-template-columns: 1fr auto;
    //         align-items: flex-end;
    //         padding: 40px 80px;
    //         cursor: pointer;
    //         &:hover { .v-play { &__wrapper { &-layer { transform: scale(1); opacity: 0 } } } }
    //     }
    //
    //     &__caption {
    //         position: relative;
    //         color: white;
    //         &-title { @include h(4, inherit); margin-bottom: 10px }
    //         &-text  { font-size: 14px }
    //     }
    //
    //     //&__cover, &__broadcaster { @include img-stretch }
    //     //&__broadcaster { display: none }
    //     &__play { position: relative; bottom: 100px }
    //
    //     &.start-video & {
    //         &__broadcaster { display: block }
    //         &__cover       { display: none }
    //     }
    // }
</style>
