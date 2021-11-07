<template>
<div id="map"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
    name: "BaseMap",
    data() {
        return {
            accessToken: 'pk.eyJ1IjoiamFzc3VsYW4iLCJhIjoiY2tyemIxdzVwMThjcjJubjh1Z21ibTI4YyJ9.NEU2B4eedUTXvYNcKEaltg',
        };
    },
    mounted() {
        mapboxgl.accessToken = this.accessToken;

        new mapboxgl.Map({
            container: 'map', // container ID
            style: 'mapbox://styles/mapbox/streets-v11', // style URL
            center: [-74.5, 40], // starting position [lng, lat]
            zoom: 9 // starting zoom
        });
    },
};
</script>
