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
<router-view></router-view>
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  }
})
export default class App extends Vue {}
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
