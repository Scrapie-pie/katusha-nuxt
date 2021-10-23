<template>
  <yandex-map
    :coords="coords"
    :controls="[]"
    :zoom="zoom"
    @map-was-initialized="test"
  >

    <ymap-marker
      v-for="(location, index) in placemarks"
      hint-content="test"
      :key="index"
      :marker-id="index"
      :coords="location"
      :icon="markerIcon"
    ></ymap-marker>
  </yandex-map>
</template>

<script>
import markerIcon from '~/src/images/yandex-blue-marker.png';

export default {
  components: {},
  props: {
    placemarks: {
      type: Array,
      required: true
    },
    coords: {
      type: Array,
      required: true
    },
    zoom: {
      type: Number,
      default: 12,
      required: true
    },
  },
  data() {
    return {
      map: {},
      markerIcon: {
        layout: 'default#imageWithContent',
        imageHref: markerIcon,
        imageSize: [34, 41],
        imageOffset: [-11, -38],
        content: 'ООО КАТЮША Ай Ти',
        contentOffset: [27, 0],
        contentLayout: '<div style="color: black; height: 26px; border-left: 1px solid rgb(255 255 255 / 5%); box-sizing: border-box; font-size: 13px; display: flex; align-items: center; padding: 6px 10px 5px 5px; border-top-right-radius: 50px; border-bottom-right-radius: 50px; background-color: rgb(255 255 255 / 90%); width: max-content; white-space: nowrap; font-weight: 100;">$[properties.iconContent]</div>' // строковый HTML шаблон для контента
      }
    };
  },
  methods: {
    test(qwe) {
      // qwe.balloon.open(this.coords, {
      //   contentBody: [
      //     '<i>Офис:</i>',
      //     '<br/>',
      //     '<strong>Название</strong>',
      //     '<br/>',
      //     'Адрес',
      //     '<br/>',
      //   ].join('')
      // }, {
      //   // Опция: не показываем кнопку закрытия.
      //   closeButton: false,
      //   panelMaxMapArea: 0
      // });
    },
    getDataCluster(obj) {
      const clust = this.map.geoObjects.get(0);
      this.map.setBounds(clust.getBounds());
      this.$emit("set-coords", obj.get("coords"));
      this.$emit("get-data-point", obj.get("coords").join());
    },
    getDataPoint(obj) {
      const coords = obj.get("coords");
      this.$emit("set-coords", coords);
      this.$bus.$emit("get-data-point", coords.join());
    },
    initHandler(obj) {
      this.map = obj;
    }
  }
};
</script>

<style scoped>
.ymap-container {
  width: 100%;
  height: 100%;
}

.cluster-icon {
  background: lime;
  color: tomato;
}
</style>
