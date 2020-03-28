<template>
  <div
    class="online-vue-editor"
    @mouseenter="hovering = true"
    @mouseleave="hovering = false"
  >
    <div class="online-vue-editor-preview">
      <slot name="preview"></slot>
    </div>
    <div class="online-vue-editor-editor">
      <slot v-if="showCode" name="editor"></slot>
      <div class="online-vue-editor-editor-button" @click="handleClickButton">
        <transition name="arrow-slide">
          <span
            class="tringle"
            :class="{hovering: hovering, reverse: showCode}"
          ></span>
        </transition>
        <transition name="text-slide">
          <span v-show="hovering">{{ controlText }}</span>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
import 'prismjs/themes/prism-tomorrow.css'
//vue-prism-editor dependency
import 'vue-prism-editor/dist/VuePrismEditor.css'
export default {
  name: 'OnlineVueLayout',
  data() {
    return {
      showCode: false,
      hovering: false
    }
  },
  computed: {
    controlText() {
      return this.showCode ? '隐藏代码' : '显示代码'
    }
  },
  methods: {
    handleClickButton() {
      this.showCode = !this.showCode
    }
  }
}
</script>

<style lang="less">
.online-vue-editor {
  @primary-color: #409eff;

  display: flex;
  flex-direction: column;
  width: 100%;
  margin: 30px auto;
  border: 1px solid #ebebeb;
  background: #fff;
  border-radius: 3px;
  transition: 0.2s;

  code {
    font-family: Menlo, Monaco, Consolas, Courier, monospace;
  }
  pre[class*='language-'] {
    font-size: 12px;
    padding: 1.5rem;
  }

  &:hover {
    box-shadow: 0 0 8px 0 rgba(232, 237, 250, 0.6),
      0 2px 4px 0 rgba(232, 237, 250, 0.5);
  }

  &-preview {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    min-height: 100px;
  }

  &-editor {
    &-button {
      border-top: solid 1px #eaeefb;
      height: 44px;
      box-sizing: border-box;
      background-color: #fff;
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
      text-align: center;
      margin-top: -1px;
      color: #d3dce6;
      cursor: pointer;
      position: relative;

      &.is-fixed {
        position: fixed;
        bottom: 0;
        width: 868px;
      }

      .text-slide-enter,
      .text-slide-leave-active {
        opacity: 0;
        transform: translateX(10px);
      }

      > span {
        position: absolute;
        transform: translateX(-30px);
        font-size: 14px;
        line-height: 44px;
        transition: 0.3s;
        display: inline-block;
      }

      > .tringle {
        position: absolute;
        width: 0;
        line-height: 44px;
        height: 0;
        top: 8px;
        border: 8px solid transparent;
        border-bottom: 12px solid #d3dce6;

        &.reverse {
          top: 16px;
          border: 8px solid transparent;
          border-top: 12px solid #d3dce6;
        }

        &.hovering {
          transform: translateX(-50px);
        }
      }
      &:hover {
        color: #409eff;
        background-color: #f9fafc;
        .tringle {
          border: 8px solid transparent;
          border-bottom: 12px solid #409eff;
        }
        .tringle.reverse {
          border: 8px solid transparent;
          border-top: 12px solid #409eff;
        }
      }
    }
  }
}
</style>
