<template>
  <div class="col-xs-12 col-sm-6">
    <p v-if= !server>Server Details are currently not updated</p>
    <p v-else># {{ server.id }} selected, Status: {{ server.status }} </p>
    <hr>
    <button @click="resetStatus">Change to Normal</button>
  </div>
</template>

<script>
import { eventBus } from '../../main.js'

export default {
  data () {
    return {
      server: 'null'
    }
  },
  methods: {
    resetStatus () {
      this.serverStatus = 'normal'
    }
    
    // ToDo: Create a method called resetStatus that takes server.status and sets it to a string of Normal
  },
  created () {
    eventBus.$on('changeServer', (server) => {
      this.serverStatus = server
    })
    // ToDo: Set the server variable from above equal to the the server data coming through the event bus using eventBus.$on('customEventName', (server) => {
    //   set data here
    // })
  }
}
</script>
