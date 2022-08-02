<template>
  <base-table
    :data="table.data"
    :columns="table.columns"
    thead-classes="text-primary"
  >
    <template slot-scope="{ row }">
      <td style="min-width: 90px">{{ row.place }}</td>
      <td style="text-align: center">{{ row.category }}</td>
      <td>{{ row.amount }}</td>
    </template>
  </base-table>
</template>
<script>
import { BaseTable } from "@/components";
export default {
  components: {
    BaseTable,
  },
  computed: {
    table() {
      return this.$t("dashboard.usersTable");
    },
  },
};
</script>
<style>
</style>
