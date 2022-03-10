<template>
  <div>
    <button @click="onClick">Click me {{ counter }}</button>
  </div>
</template>

<script>
export default {
  name: "MyButtonVue",
  data() {
    return {
      counter: 0,
      
    };
  },
  methods: {
    onClick() {
      this.counter++;
    },
    onMouseOver(){
        
        console.log('mouseover')
    }
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  // hook created - Операции с доступными свойствами компонента
  created() {
    console.log("creared");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    const btn = this.$el.querySelector("button");
    if (btn) {
      btn.addEventListener("mouseover", this.onMouseOver);
    }
    console.log("mounted");
    // debugger
  },
  beforeUpdate(){
      console.log('beforeUpdate')
  },
  updated(){
      console.log('updated')
  }
};
</script>

<style lang="less" scoped>
</style>
