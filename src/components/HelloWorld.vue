<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ firstName }}</h1>
    <h1>{{ lastName }}</h1>
    <h1>{{ fullName }}</h1>
    <h5>{{ counter }}</h5>
    <button @click="incrementCounter">press me</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
  counter = 0;
  firstName = 'Leskhan';
  lastName = 'Karatayev';
  zip: string | undefined;
  get fullName(): string {
    return this.firstName + ' ' + this.lastName;
  }
  incrementCounter() {
    this.counter++;
  }
  mounted(){
    this.zip ='da'
    console.log('mounted '+this.zip)
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
