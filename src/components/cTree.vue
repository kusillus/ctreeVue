<template>
  <li>
    <div
      :class="{bold: isFolder}"
      @click="toggle"
      >
      {{model.name}}
    </div>
    <ul v-show="open" v-if="isFolder">
      <item
        class="child"
        v-for="model in model.children"
        :model="model">
      </item>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'item',
  props: {
    model: Object
  },
  data () {
    return {
      open: true
    }
  },
  computed: {
    isFolder: function () {
      return this.model.children &&
        this.model.children.length
    }
  },
  methods: {
    toggle: function (el) {
      console.log(el)
      if (this.isFolder) {
        this.open = !this.open
      }
    }
  }
}
</script>

<style lang="scss">
  .open:before, .close:before {
    content: '';
    background-color: red;
    width: 1rem;
    // height: 1rem;
    position: absolute;
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
  .child{
    margin: 1rem .2rem;
    display: block;
    border: .1rem solid gray;
    border-radius: .2rem;
    padding: .5rem;
  }
  .bold {
    font-weight: 800;
  }
</style>
