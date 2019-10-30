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
    this.$router.push({ path: 'user', query: { id: id.toString() }})
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
