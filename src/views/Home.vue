<template>
<div>
    <!-- <BaseMap /> -->
    <NavBar />
    <HomeTable />
</div>
</template>

<script>
// @ is an alias to /src
import HomeTable from "@/components/HomeTable.vue";
// import BaseMap from "@/components/BaseMap.vue";
import NavBar from "@/components/NavBar.vue";
export default {
    name: "Home",
    components: {
        // BaseMap,
        HomeTable,
        NavBar
    }
};
</script>
