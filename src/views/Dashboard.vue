<template>
  <div>
    <h1>Dashboard</h1>
    <p class="text-center">Hello {{ userName }}, you are logged in.</p>
    <p class="w-full text-center my-8">
      <a
        class="bg-grey-dark hover:bg-grey-darker text-white font-bold py-2 px-4 m-2 rounded cursor-pointer"
        @click.prevent="alert('This is a test message.', 'success')"
      >
        Test Alert
      </a>
    </p>
  </div>
</template>

<script>
import bus from '@/bus'
import { mapGetters } from 'vuex'

export default {
  data () {
    return {

    }
  },
  computed: {
    ...mapGetters([
      'userName'
    ])
  },
  methods: {
    alert (message, level) {
      bus.$emit('flash', message, level)
    }
  }
}
</script>
