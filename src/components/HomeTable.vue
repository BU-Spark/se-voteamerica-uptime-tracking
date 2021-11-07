<template>
  <div v-bind:style="styleTable">
    <md-table v-model="services" md-sort="name" md-sort-order="asc" md-card>
      <md-table-toolbar>
        <h1 class="md-title">Services</h1>
      </md-table-toolbar>

      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Description" md-sort-by="description">{{
          item.description
        }}</md-table-cell>
        <md-table-cell v-if=item.status md-label="Status" md-sort-by="status">{{
          item.status
        }}</md-table-cell>
        <md-table-cell v-else md-label="Status" md-sort-by="status">-</md-table-cell>
        <md-table-cell v-if=item.status_changed_at md-label="Status Changed At" md-sort-by="status_changed_at">{{
          item.status_changed_at.substring(0,10)
        }}</md-table-cell>
        <md-table-cell v-else md-label="Status Changed At" md-sort-by="status_changed_at">-</md-table-cell>
        <md-table-cell v-if=item.uptime_day md-label="Uptime Day" md-sort-by="uptime_day">{{
          Number((item.uptime_day).toFixed(5))
        }}</md-table-cell>
        <md-table-cell v-else md-label="Uptime Day" md-sort-by="uptime_day">-</md-table-cell>
        <md-table-cell v-if=item.uptime_week md-label="Uptime Week" md-sort-by="uptime_week">{{
          Number((item.uptime_week).toFixed(5))
        }}</md-table-cell>
        <md-table-cell v-else md-label="Uptime Week" md-sort-by="uptime_week">-</md-table-cell>
        <md-table-cell v-if=item.uptime_month md-label="Uptime Month" md-sort-by="uptime_month">{{
          Number((item.uptime_month).toFixed(5))
        }}</md-table-cell>
        <md-table-cell v-else md-label="Uptime Month" md-sort-by="uptime_month">-</md-table-cell>
        <md-table-cell v-if=item.uptime_quarter md-label="Uptime Quarter" md-sort-by="uptime_quarter">{{
          Number((item.uptime_quarter).toFixed(5))
        }}</md-table-cell>
        <md-table-cell v-else md-label="Uptime Quarter" md-sort-by="uptime_quarter">-</md-table-cell>
        <md-table-cell v-if=item.url md-label="Links" md-sort-by="url">
          <a target="_blank" :href=item.url>Link</a>
        </md-table-cell>
        <md-table-cell v-else md-label="Links" md-sort-by="url">-</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>
<script>
export default {
  name: "HomeTable",
  data() {
    return {
        services:[{},],
        styleTable: {
                display: 'inline-block',
                position: 'absolute',
                top: '0',
                bottom: '5%',
                width: '45%',
                right: '5%',
            },
    };
  },
  async mounted() {
      const response = await fetch("http://vapre.us.to:9901/v1/uptime/sites/")
        .then(results => { return results.json()});
      this.services = response.results;
      console.log(this.services);
  },
};
</script>