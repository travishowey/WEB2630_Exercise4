<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <!-- ToDo: Use the Server component selector with the name you gave it below -->
      <li  v-for='server in servers' :key="server">
        <div v-for="(value) in server" :key="value">
          Server # {{ value }}
        </div>
      </li>
      <!-- ToDo: Pass server as a property to the Server component (remember to bind to the property name from Server.vue) -->
    </ul>
    <appServer></appServer>
  </div>
</template>

<script>
import { Server } from './Server.vue'

export default {
  data () {
    return {
      servers: [
        { id: 1, status: 'Normal' },
        { id: 2, status: 'Critical' },
        { id: 3, status: 'Unknown' },
        { id: 4, status: 'Normal' }
      ]
    }
  },
  components: {
      appServer: Server
  }
}
</script>
