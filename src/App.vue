<template>
  <v-app>
    <v-content>
      <v-container>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
        <router-view/>
      </v-container>
    </v-content>
  </v-app>
</template>

<style>
</style>
