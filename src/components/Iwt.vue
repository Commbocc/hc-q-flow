<template lang="html">
  <table class="table table-sm table-striped table-bordered">
    <thead class="bg-secondary text-white">
      <tr>
        <th>Service</th>
        <th>Location</th>
        <th>Customers Waiting</th>
        <th>Apprx. Wait Time</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="n in 10">
        <td>Apply for a Building Permit</td>
        <td>County Center</td>
        <td>{{ n }}</td>
        <td>{{ n }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
}
</script>
