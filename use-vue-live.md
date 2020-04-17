使用 `vue-live` 与本插件的 `layout` 搭配

```vue
<template>
  <vue-live :layout="OnlineVueLayout" :code="code"/>
</template>

<script>
import { VueLive } from "vue-live";
import { OnlineVueLayout } from 'online-vue-editor'

export default {
  components: {
    VueLive
  },
  data() {
    return {
      OnlineVueLayout,
      code: `<input type='button' value='I am ccc' />`
    }
  }
}
</script>
```