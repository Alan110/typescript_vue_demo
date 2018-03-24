<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <router-view/> -->
    <hello></hello>
  </div>
</template>

<script lang="ts">
import { Component, Emit, Inject, Model, Prop, Provide, Vue, Watch } from 'vue-property-decorator'
import hello from './components/Hello.vue'

@Component({
  components: {
    hello
  }
})
export default class app extends Vue {
  name: 'app'

  @Prop()
  propA: number

  @Prop({ default: 'default value' })
  propB: string

  @Prop([String, Boolean])
  propC: string | boolean

  @Prop({ type: null })
  propD: any

  @Watch('child', {deep: true})
  onChildChanged (val: string, oldVal: string) { }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
