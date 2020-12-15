<template>
    <div style="height: 500px; width: 100%">
        

      <l-map
      v-if="showMap"
      :zoom="zoom"
      :center="center"
      :options="mapOptions"
      style="height: 80%"
      @update:center="centerUpdate"
      @update:zoom="zoomUpdate"
      >

        <l-tile-layer
          :url="url"
          :attribution="attribution"
        />

        <l-marker ref="marker"
          v-for="(retailer, index) in retailers"
          :key="retailer.id" 
          :icon="icon"
          :lat-lng="getPos(retailer.latitude,retailer.longitude)"
          id="marker"
          @mouseover="$event.target.openPopup()" v-on:mouseover="test(index)">

              <l-popup class="popup">
                <div @click="innerClick(retailer)">
                  {{retailer.name}}
                  {{ retailer.storeName }}
                  <br>
                  {{ retailer.storeType }}
                  <p v-show="showParagraph">
                    {{retailer.description}}
                  </p>
                </div>
              </l-popup>
            


        </l-marker>

      </l-map>
  </div>
    
</template>





<script>
import { latLng, icon } from "leaflet";
import { LMap, LTileLayer, LMarker, LPopup } from "vue2-leaflet";

    export default {
        name: "Map",
        components: {
            LMap,
            LTileLayer,
            LMarker,
            LPopup,
        },
        props: ['retailers'],
    data() {
        return {
          zoom: 13,
          center: latLng(45.7462373, 4.8339948), 
          url: 'http://{s}.tile.stamen.com/toner-lite/{z}/{x}/{y}.png',
          attribution:
              '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
          currentZoom: 11.5,
          currentCenter: latLng(45.7462373, 4.8339948),
          showParagraph: false,
          mapOptions: {
              zoomSnap: 0.5
          },
          showMap: true,
          retailer: '',
          icon: icon({
            iconUrl: "https://dgudge.com/eggsnow.png",
            iconSize: [32, 37],
            iconAnchor: [16, 37]
          }),
        }
  },
  methods: {
    zoomUpdate(zoom) {
      this.currentZoom = zoom;
    },
    centerUpdate(center) {
      this.currentCenter = center;
    },
    showLongText() {
      this.showParagraph = !this.showParagraph;
    },
    innerClick(retailer) {
      this.$router.replace({
                    name: 'Retailer', params: {id: retailer.id, retailer: retailer}
                });
      //console.log(retailer.id);
    },
    getPos(lat, long) {
      return latLng(lat,long);
    },
    test(e) {
      console.log(e);
      console.log(this.retailers[e]);
      //this.retailers[e].marker.openPopup();

    }
  },
  computed: {
    dynamicSize() {
      return [this.iconSize, this.iconSize * 1.15];
    },
    dynamicAnchor() {
      return [this.iconSize / 2, this.iconSize * 1.15];
    }
  },
  mounted(){ 
  }
}
</script>


<style>
#map {
    background-color: #f3f3f3;
}
.popup {
  size:150;
  color:black;
  /*
  height: 150px;
  width: 200px;
  */
}
.leaflet-marker-icon {
  /*
  background-color: black;
  */
  size: 200%;
  height: 200%;
}

.leaflet-popup-content-wrapper, .leaflet-popup-tip {
    background: #f59e20;
    color: #fff;
    box-shadow: 0 3px 14px rgba(255, 255, 255, 0.4);
    border: none;
    border-radius: 0px;
}

.leaflet-container a.leaflet-popup-close-button {
    color: #000;
}


.leaflet-container a.leaflet-popup-close-button:hover {
    color: #fff;
}

.list-group-item {
    position: relative;
    display: block;
    padding: 0.75rem 1.25rem;
    background-color: #f59e20;
    border-bottom: 3px solid rgb(255, 255, 255);
}

.card-title {
    margin-bottom: 0.75rem;
    font-size: 25px;
    font-family: 'avenir';
    font-weight: 700;
}

</style>