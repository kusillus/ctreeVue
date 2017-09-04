<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <!-- <cTree></cTree> -->
      <!-- the demo root element -->
    <ul>
      <item
        class="list"
        :model="treeData">
      </item>
    </ul>
  </div>
</template>

<script>
import item from './components/cTree.vue'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      // demo data
      treeData: {
        name: 'Padre',
        children: [
          { name: '1er Hijo' },
          { name: '2do Hijo' },
          {
            name: '1er nieto',
            children: [
              { name: '1er bisnieto folder' },
              { name: '2do bisnieto folder' },
              { name: '3er bisnieto folder' }
            ]
          }
        ]
      }

    }
  },
  components: {
    item
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
.list{
  border: .1rem solid gray;
  border-radius: .2rem;
  margin: 1rem .2rem;
  padding: 1rem;
  // background-color: red;
  display: block;
  // width: 100%;
  text-align: left;
}
</style>
