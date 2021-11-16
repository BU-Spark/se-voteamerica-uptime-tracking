<template>
<div>    
    
    <NavBar />

    <h3 style="margin-top: 90px;"
    > We have a problem ______
(facts that change every 10 seconds) </h3>

<div style="display: inline-block';
                position: absolute;
                bottom: 5%;
                width: 40%;
                height: 60%;
                left: 5%; border: 2px solid black;"> 
    <h3> Sites current status</h3>
    <BaseMap /> 
    
    </div>
    
    <div style="display: inline-block';
                position: absolute;
                bottom: 5%;
                width: 40%;
                height: 60%;
                left: 55%; border: 2px solid black;"> 
    <h3> Sites downtime rank</h3>
    </div>
</div>


</template>

<script>
// @ is an alias to /src
import BaseMap from "@/components/BaseMap.vue";
import NavBar from "@/components/NavBar.vue";
export default {
    name: "Home",
    components: {
        BaseMap,
        NavBar
    }
};
</script>
