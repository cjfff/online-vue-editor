引入组件库

```vue
<template>
  <online-vue-editor :code="`<template>
  <el-button @click='click'>这是element-ui的按钮 {{msg}}</el-button>
</template> 
<script>

export default {
  data() {
    return {
      msg: 'hello worlld'
    }
  },
  methods: {
    click() {
      alert('hello')
    }
  }
}
</script>`"/>
</template>


```