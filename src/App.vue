<template>
<div>
<nav class="NavBar">
<ul>
<li>
<router-link to="/">Home</router-link>
</li>
<li>
<router-link to="/about">About</router-link>
</li>
</ul>
</nav>
<br/>
<button @click="selectUserHandler">User</button>
<button @click="selectPostHandler('1')">Post 1</button>
<button @click="selectPostHandler('2')">Post 2</button>
<button @click="selectPostHandler('3')">Post 3</button>
<router-view></router-view>
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  }
})
export default class App extends Vue {
  selectUserHandler(){
    const id = Math.floor(Math.random() * 10);
    this.$router.push({ name: 'user', query: { id: id.toString() }})
  }

  selectPostHandler(id: string){
      this.$router.push({ name: 'post', params: { id: id }})
  }
}
</script>

<style lang="scss">
.NavBar{
  ul{
    li{
      display: inline-block;
      padding-left:2vh;
    }
  }

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
}
</style>
