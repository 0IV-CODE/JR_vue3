<script lang="ts">
import { defineComponent } from 'vue';
import { useTheme } from 'vuetify';
// import { RouterLink } from 'vue-router';

export default defineComponent({
  name: 'AppBar',
  setup() {
    const theme = useTheme();

    const toggleTheme = () => {
      theme.global.name.value = theme.global.name.value === 'dark' ? 'light' : 'dark';
    };

    return {
      theme,
      toggleTheme,
    };
  },
});
</script>

<template>
  <v-app-bar flat color="primary" dark>
    <v-toolbar-title>HVAC Company</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn text to="/" tag="RouterLink">Home</v-btn>
    <v-btn text to="/services" tag="RouterLink">Services</v-btn>
    <v-btn text to="/about" tag="RouterLink">About Us</v-btn>
    <v-btn text to="/contact" tag="RouterLink">Contact</v-btn>
    <v-btn @click="toggleTheme" outlined>
      {{ theme.global.name.value === 'dark' ? 'Light' : 'Dark' }} Theme
    </v-btn>
  </v-app-bar>
</template>

<style scoped>
.v-app-bar {
  padding: 0 20px;
}
</style>
