# online-vue-editor

[![Build Status](https://badgen.net/travis/cjfff/online-vue-editor/master)](https://travis-ci.com/cjfff/online-vue-editor)
[![NPM Download](https://badgen.net/npm/dm/@cjfff/online-vue-editor)](https://www.npmjs.com/package/@cjfff/online-vue-editor)
[![NPM Version](https://badge.fury.io/js/%40cjfff%2Fonline-vue-editor.svg)](https://www.npmjs.com/package/@cjfff/online-vue-editor)
[![NPM License](https://badgen.net/npm/license/@cjfff/online-vue-editor)](https://github.com/cjfff/online-vue-editor/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/cjfff/online-vue-editor/pulls)
[![Automated Release Notes by gren](https://img.shields.io/badge/%F0%9F%A4%96-release%20notes-00B2EE.svg)](https://github-tools.github.io/github-release-notes/)

short description + sample image(png/gif/mp4)

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Install](#install)
- [Usage](#usage)
- [Links](#links)
- [Contributing](#contributing)
- [Contributors](#contributors)
- [License](#license)

## Introduction

本插件为 `vue-live` 的一个 `layout` 皮肤

即组件使用方式可以参考或者使用[原仓库](https://github.com/vue-styleguidist/vue-live)

引用 `layout` 可以引用本插件

[⬆ Back to Top](#table-of-contents)

## Features

[⬆ Back to Top](#table-of-contents)

## Install

```js
npm i "online-vue-editor"
```

[⬆ Back to Top](#table-of-contents)

## Usage

### 不安装 `vue-live` 使用, 全局安装

```js
import Vue from 'vue'
import OnlineVueEditor from 'online-vue-editor'

Vue.use(OnlineVueEditor)
```

### 不安装 `vue-live` 使用, 局部安装

```vue
<template>
  <online-vue-editor :code="code" />
</template>

<script>
import OnlineVueEditor from 'online-vue-editor'

export default {
  components: {
    OnlineVueEditor
  },
  data() {
    return {
      code: `<input type='button' value='I am ccc' />`
    }
  }
}
</script>
```

### 安装 `vue-live` ，使用本库作为 layout 引入 -- 推荐

此种方式可以不受限于此库享受 `vue-live` 的最新支持，所以推荐此种使用方式

```vue
<template>
  <vue-live :layout="OnlineVueLayout" :code="code" />
</template>

<script>
import {VueLive} from 'vue-live'
import {OnlineVueLayout} from 'online-vue-editor'

export default {
  components: {
    VueLive,
    OnlineVueEditor
  },
  data() {
    return {
      code: `<input type='button' value='I am ccc' />`
    }
  }
}
</script>
```

[⬆ Back to Top](#table-of-contents)

## Links

- [docs](https://cjfff.github.io/online-vue-editor/)

[⬆ Back to Top](#table-of-contents)

## Contributing

For those who are interested in contributing to this project, such as:

- report a bug
- request new feature
- fix a bug
- implement a new feature

Please refer to our [contributing guide](https://github.com/FEMessage/.github/blob/master/CONTRIBUTING.md).

[⬆ Back to Top](#table-of-contents)

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

[⬆ Back to Top](#table-of-contents)

## License

[MIT](./LICENSE)

[⬆ Back to Top](#table-of-contents)
