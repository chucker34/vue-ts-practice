<template>
  <div class="about">
    <Play propsMsg="ここでいろいろ遊んでいく"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Play from '@/components/Play.vue'; // @ is an alias to /src

@Component({
  components: {
    Play,
  },
})
export default class Abount extends Vue {}
</script>