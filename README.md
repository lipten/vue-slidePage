# vue-slidePage

### Introduction

vue-slidePage is a fullscreen scrolling component of Vue.js, Based on [slidePage](https://github.com/lipten/slidePage)

### Demo

* [simple](http://lipten.link/projects/slidePage3/examples/simple.html)
* [custom](http://lipten.link/projects/slidePage3/examples/custom.html)

### Usage

#### Install

```bash
$ npm i -S vue-slidepage
```

Work on a Vue instance:

```HTML
<slide-container>
  <slide-page v-for="(item, index) in list">
    <h2>{{item.name}}</h2>
  </slide-page>
</slide-container>
```

```JavaScript
import { SlideContainer, SlidePage } from 'vue-slidePage'

new Vue( {
  el: 'body',
  data () {
    return {
      list: [
        {name: 'Page1'},
        {name: 'Page2'},
        {name: 'Page3'},
      ],
    }
  },
  components: {
    SlideContainer,
    SlidePage
  }
} )
```

## Props

SlideContainer:

<table>
  <thead>
  <tr>
    <th>name</th>
    <th>type</th>
    <th>default</th>
    <th>description</th>
  </tr>
  </thead>
  <tbody>
    <tr>
      <td>useAnimation</td>
      <td>Boolean</td>
      <td>true</td>
      <td>是否开启动画</td>
    </tr>
    <tr>
      <td>refresh</td>
      <td>Boolean</td>
      <td>true</td>
      <td>每次滚动进入是否重新执行动画</td>
    </tr>
    <tr>
      <td>useWheel</td>
      <td>Boolean</td>
      <td>true</td>
      <td>是否开启鼠标滚轮滑动</td>
    </tr>
    <tr>
      <td>useSwipe</td>
      <td>Boolean</td>
      <td>true</td>
      <td>是否开启移动端触控滑动</td>
    </tr>
  </tbody>
</table>

### Events

SlideContainer:

<table>
  <thead>
  <tr>
    <th>name</th>
    <th>description</th>
    <th>$event</th>
  </tr>
  </thead>
  <tbody>
    <tr>
      <td>before</td>
      <td>每次全屏滚动前触发事件，回调三个参数(origin, direction, target)，分别是滚动前的page序号、方向('next'/'prev')、滚动后的page序号</td>
      <td>$event.before</td>
    </tr>
    <tr>
      <td>after</td>
      <td>次全屏滚动后触发事件，回调三个参数(origin, direction, target)，参数释义同上</td>
      <td>$event.after</td>
    </tr>
  </tbody>
</table>

## Slots

SlidePage:

<table>
  <thead>
  <tr>
    <th>name</th>
    <th>description</th>
  </tr>
  </thead>
  <tbody>
    <tr>
      <td>default</td>
      <td>Page's content</td>
    </tr>
  </tbody>
</table>

usage:
```HTML
<slide-container>
  <slide-page>
    <img src="">
    <p></p>
    <button></button>
  </slide-page>
</slide-container>
```

# License
MIT
