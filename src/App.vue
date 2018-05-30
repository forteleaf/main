<template>
  <v-app>
    <Nav/>
  </v-app>
</template>

<script>
import Nav from '@/components/Nav'
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Nav
  }
}
</script>
