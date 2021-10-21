<template>
  <div>
    <md-table v-model="services" md-sort="name" md-sort-order="asc" md-card>
      <md-table-toolbar>
        <h1 class="md-title">Services</h1>
      </md-table-toolbar>

      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Description" md-sort-by="description">{{
          item.description
        }}</md-table-cell>
        <md-table-cell md-label="Status" md-sort-by="status">{{
          item.status
        }}</md-table-cell>
        <md-table-cell md-label="Status Changed At" md-sort-by="status_changed_at">{{
          item.status_changed_at
        }}</md-table-cell>
        <md-table-cell md-label="Uptime Day" md-sort-by="uptime_day">{{
          item.uptime_day
        }}</md-table-cell>
        <md-table-cell md-label="Uptime Week" md-sort-by="uptime_week">{{
          item.uptime_week
        }}</md-table-cell>
        <md-table-cell md-label="Uptime Month" md-sort-by="uptime_month">{{
          item.uptime_month
        }}</md-table-cell>
        <md-table-cell md-label="Uptime Quarter" md-sort-by="uptime_quarter">{{
          item.uptime_quarter
        }}</md-table-cell>
        <md-table-cell md-label="Links" md-sort-by="url">{{
          item.url
        }}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>
<script>
export default {
  name: "HomeTable",
  data() {
    return {
        services:[{
        //   id: 1,
        //   description: 'VT Polling Place Lookup, Voter Registration Status Verifier, Absentee Ballot Request, and Absentee Ballot Tracker',
        //   status: 'up',
        //   statusChangedAt: '06/10/2021 2:39 a.m.',
        //   uptimeDay: '99.00%',
        //   upTimeWeek: '100.00%',
        //   uptimeMonth: '100.00%',
        //   upTimeQuarter: '100.00%',
        //   links: "links"
        // },
        // {
        //   id: 2,
        //   description: 'IN Absentee Ballot Request',
        //   status: 'up',
        //   statusChangedAt: '06/20/2021 12:27 a.m.',
        //   uptimeDay: '100.00%',
        //   upTimeWeek: '100.00%',
        //   uptimeMonth: '100.00%',
        //   upTimeQuarter: '100.00%',
        //   links: "links"
        // },
        // {
        //   id: 3,
        //   description: 'IN Polling Place Lookup, Online Voter Registration, Voter Registration Status Verifier, and Absentee Ballot Tracker',
        //   status: 'up',
        //   statusChangedAt: '07/02/2021 5:46 a.m.',
        //   uptimeDay: '100.00%',
        //   upTimeWeek: '100.00%',
        //   uptimeMonth: '100.00%',
        //   upTimeQuarter: '100.00%',
        //   links: "links"
        },]
    };
  },
  async mounted() {
      // const serviceInfo = await fetch("http://vapre.us.to:9901/v1/uptime/sites/");
      // this.services = serviceInfo;
      // console.log(this.services.json());
      const response = await fetch("http://vapre.us.to:9901/v1/uptime/sites/")
        .then(results => { return results.json()});
      this.services = response.results;
      console.log(this.services);
  },
};
</script>