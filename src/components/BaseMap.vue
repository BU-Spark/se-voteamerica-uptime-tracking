<template>
<div id="map" v-bind:style="styleMap"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
    name: "BaseMap",
    data() {
        return {
            accessToken: 'pk.eyJ1IjoiamFzc3VsYW4iLCJhIjoiY2tyemIxdzVwMThjcjJubjh1Z21ibTI4YyJ9.NEU2B4eedUTXvYNcKEaltg',
            styleMap: {
                display: 'inline-block',
                position: 'absolute',
                top: '0',
                bottom: '5%',
                width: '40%',
                height: '40%',
                left: '5%',
            },
        };
    },
    mounted() {
        mapboxgl.accessToken = this.accessToken;

        new mapboxgl.Map({
            container: 'map', // container ID
            style: 'mapbox://styles/mapbox/streets-v11', // style URL
            center: [-94.74, 39.12], // starting position [lng, lat]
            zoom: 2.6 // starting zoom
        });
    },
};
</script>
