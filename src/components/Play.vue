<template>
  <div class="play">
    <h1>{{ propsMsg }}</h1>
    <ul id="example-1">
      <li v-for="item in items">
        {{ item.message }}
      </li>
    </ul>
    <input v-model="inputItem">
    <button @click="add">更新</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Play extends Vue {
    @Prop() private propsMsg!: string;

    inputItem: string = ''

    items = [
      { message: 'hoge' },
      { message: 'fuga' }
    ]

    add () {
      if (this.inputItem) {
        this.items.push({ message: this.inputItem })
        this.inputItem = ''
      }
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
