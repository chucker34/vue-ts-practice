<template>
  <div class="play">
    <h1>{{ displayMsg }}</h1>
    <input v-model="inputMsg">
    <button @click="update">更新</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Play extends Vue {
    @Prop() private propsMsg!: string;

    inputMsg: string = '';

    displayMsg: string = this.propsMsg

    update () {
        this.displayMsg = this.propsMsg + this.inputMsg
        this.inputMsg = ''
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
