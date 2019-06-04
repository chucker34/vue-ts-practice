<template>
  <div class="play">
    <h1>{{ propsMsg }}</h1>
    <v-list id="example-1">
      <li v-for="item in items">
        {{ item.message }}
      </li>
    </v-list>
    <v-card>
      <v-card-title><h3>なんか追加してみ</h3></v-card-title>
      <v-card-text>好きにやっちゃってー</v-card-text>
      <v-form>
        <v-text-field  autofocus=true label="ここに入力してください" v-model="inputItem"></v-text-field>
        <v-btn color='success' @click="add" class='usa-button'>更新</v-btn>
      </v-form>
    </v-card>
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

<style scoped>

</style>
