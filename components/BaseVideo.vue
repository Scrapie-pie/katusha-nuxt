<template>
    <div class="video" @click="" :class="this.classInit">
      <div class="video__cover">
        <img class="video__preview" :src="preview">
        <BaseIcon icon="play_video" class="video__play"/>
        <div class="video__broadcaster">
          <iframe class="video__broadcaster" width="560" height="315" frameborder="0" allowfullscreen :src="this.srcInit"></iframe>
        </div>

      </div>
      <div v-if="caption" class="video__caption">
        {{caption}}
      </div>
    </div>
</template>

<script>



export default {
    name: "BaseVideo",
    components: {},
    data:() => ({
        url: "https://www.youtube.com/embed/JwpFvFpbOGc" + "?" + "autoplay=1",
        isStarted: false,
    }),
    props: {
      startVideo: {
        type: Boolean,
         default: false
      },
      preview: {
        type: String,
        default: require("@/src/images/video-preview01.jpg") // temp
      },
      caption: String,
    },
    computed: {
      //srcInit()   { return this.startVideo ? this.url : null },
      srcInit()   {
        return this.isStarted ? this.url : ""
     },
     classInit() {
        return this.isStarted ? "start-video" : "video_stoped"
     },
      //classInit() { return true },
    }
}
</script>

<style lang="scss">
    .video {
        position: relative;
        //width: 100%;
        //height: 100%;

        overflow: hidden;
        @include flex-container(column, 15px);
        //width: min-content;
        //width: 100%;
        //width: 560px;
        //height: 315px;


        &__cover {
            cursor: pointer;
            //background-color: red;
            height: 100%;
            width: 100%;
            //padding: 20px;
            //position: absolute;
            position: relative; // absolute ?
            left: 0;
            right: 0;
            top: 0;
            bottom: 0;
            //border-radius: 10px;
        }

        &__caption {
          font-size: 18px;
        }

        &__broadcaster {
          //width: 560px;
          //height: 315px;
          //cursor: pointer;
        }

        &__preview {
          position: absolute;
          height: 100%;
          width: 100%;
          left: 0;
          right: 0;
          top: 0;
          bottom: 0;
        }

        &__play {
          color: white;
          font-size: 102px;
          box-shadow: 0px 35px 15px -35px rgb(0 0 0 / 80%);
          transition: .2s ease-in;
          position: absolute;
          top: 50%;
          left: 50%;
          transform: translate(-50%, -50%);

        }

        &__cover:hover & {
          &__play {
            font-size: 110px;
          }
        }
    }
</style>
