<template>
  <!-- ToDo: Inside the list item tag add a click event that calls serverSelected -->
  <li class="list-group-item" @click="severSelected">
    <p># {{ server.id }}</p>
    <!-- ToDo: Output Server # {{ server.id }} -->
  </li>
</template>

<script>
import eventBus from '../../main';

export default {
  props: {
    server: {
      type:String
    }
  },
  methods: {
    serverSelected () {
      eventBus.$emit('changeServer', this.serverSelected)
      }
    // ToDo: Create serverSelected that creates a custom event that sends the server data to the eventBus (tip: eventBus.$emit('customEventName', data))
  }
}
</script>
