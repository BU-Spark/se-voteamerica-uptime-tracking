<template>
<div>
    <BaseMap />
    <HomeTable />
</div>
</template>

<script>
// @ is an alias to /src
import HomeTable from "@/components/HomeTable.vue";
import BaseMap from "@/components/BaseMap.vue";
export default {
    name: "Home",
    components: {
        BaseMap,
        HomeTable
    }
};
</script>
