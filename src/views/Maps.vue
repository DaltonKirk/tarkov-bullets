<template>
  <div>
    <img :src="activeMapImage" alt style="max-width:100%" />
    <ul>
      <MapListingItem
        v-for="map in maps"
        :map-name="map.name"
        :map-url="map.imageUrl"
        :key="map.name"
        @click.native="activeMapImage = map.imageUrl"
      ></MapListingItem>
    </ul>
  </div>
</template>

<script>
import MapListingItem from "@/components/MapListingItem.vue";
export default {
  components: {
    MapListingItem
  },
  data: function() {
    return {
      activeMapImage: "",
      maps: []
    };
  },
  methods: {
    showMap: function(imageUrl) {
      this.activeMapImage = imageUrl;
    }
  }
};
</script>

<style lang="scss" scoped>
ul {
  list-style: none;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5px;
  max-width: 720px;
  margin: 0 auto;
  padding: 0;
}
</style>