<template>
  <Model />
  <h1>{{ title }}</h1>
  <h4>{{ msg }}</h4>
  <p>{{ hobby[0] }}</p>
  <p>{{ myObj.fname }}</p>
  <p>{{ myname() }}</p>
  <img v-bind:src="src" :alt="alt">
  <img src="./assets/logo.png" alt="">
  <p><a :href="link">Google</a></p>
  <p v-text="myText"></p>
  <p v-html="myHtml"></p>
  <input type="text" ref="name">
  <button @click="handleClick">Click Here</button>
  <Model />
  <Cons />
  <p v-if="yourAge == allowedAge">
    You are good to go.
  </p>
  <p v-else-if="yourAge <= allowedAge">
    ohh you can go there....
  </p>
  <p v-else>
    you ar not allowed!
  </p>
  <hr>
  <p v-show="yourName == 'Arman' ">
    You can access now Arman>>>
  </p>
  <p v-show="yourName !== 'Arman'">
    You cannot access here....
  </p>
  <div v-if="ourCountry()">
    Our counrty name is Bangladesh
  </div>
  <div v-else>
    Ohh sorry ...
  </div>
</template>

<script>
import Model from './components/Model.vue';
import Cons from './components/Cons.vue';
export default {
  name: 'App',
  components: { Model,Cons },
  data () {
    return {
      title: 'This is my first vue app :)',
      msg: 'Our country name is Bangladesh',
      hobby: ['cricket','football'],
      myObj: {
        fname: 'Khan',
        age: 24
      },
      src: 'https://picsum.photos/id/1/200/300',
      alt: 'This is lorem Picsum',
      link: 'https://www.google.com/',
      myText: 'Hello CSE Engineer',
      myHtml: '<strong>SOUTHERN UNIVERSITY</strong>',
      yourAge: 17,
      allowedAge: 18,
      yourName: 'Arman',
      country: 'Bangladesh'
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.fucus();
    },
    myname() {
      return 'noushed';
    },
    ourCountry() {
      return this.country == 'Bangladesh' ? true : false;
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid black;
}
h4{
  color: red;
}
p{
  border: 1px solid black;
}
</style>
