<template>
  <vue-live
    :layout="OnlineVueLayout"
    :code="code"
    :components="components"
    :delay="delay"
    :requires="requires"
    :layout-props="layoutProps"
    :jsx="jsx"
    v-bind="$attrs"
    v-on="$listeners"
  ></vue-live>
</template>

<script>
import {VueLive} from 'vue-live'
import OnlineVueLayout from './online-vue-layout.vue'

const UPDATE_DELAY = 300

export default {
  name: 'OnlineVueEditor',
  components: {
    VueLive
  },
  props: {
    /**
     * 需要展示的代码
     */
    code: {
      type: String,
      required: true
    },
    /**
     * 传入你需要的 layout
     */
    layout: {
      type: Object,
      default: undefined
    },
    /**
     * 传入你要注册的组件对象
     * @example { DatePicker: VueDatePicker }
     * @example { VueDatePicker }
     */
    components: {
      type: Object,
      default: () => {}
    },
    /**
     * 传入你要获取的 node 包
     * @example { lodash: require("lodash") }
     * @example { moment: require("moment") }
     */
    requires: {
      type: Object,
      default: () => {}
    },
    /**
     * 代码修改后的更新间隔
     */
    delay: {
      type: Number,
      default: UPDATE_DELAY
    },
    /**
     * jsx渲染函数
     */
    jsx: {
      type: Boolean,
      default: false
    },
    /**
     * layout的props
     */
    layoutProps: {
      type: Object,
      default: undefined
    },
    /**
     * Props of vue-prism-editor
     * @example { lineNumbers: true }
     * @see https://github.com/koca/vue-prism-editor
     */
    editorProps: {
      type: Object,
      default: () => ({lineNumbers: true})
    },
    /**
     * Outside data to the preview
     * @example { count: 1 }
     */
    dataScope: {
      type: Object,
      default: () => ({})
    }
  },

  data() {
    return {
      OnlineVueLayout
    }
  }
}
</script>
