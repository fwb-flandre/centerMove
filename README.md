# centerMove
这能帮助你将图片垂直水平居中并随鼠标反方向移动的非线性动画（类似osu开始界面）

## 使用方法
在 main.js 中
``` javascript
import centerMove from './centerMove.js'
// 引入自定义插件
Vue.use(centerMove)
```

在项目中
``` javascript
  <div class="blogIndex" >
    <img src="../../assets/back.jpg" style="width: 115%" ref="img" v-center="move">
  </div>
  
  <script>
// export default 只是为了导出，类似 new Vue()
export default {
  name: 'blogIndex',
  data () {
    return {
    }
  },
  methods: {
    // 鼠标移动时触发该方法
    move (x, y) {
      this.$moveCenter(x, y, this.$refs.img.style, {
        xZoom: 12,
        yZoom: 5,
        xOffset: -100,
        durning: 30
      })
    }
  }
}
</script>
```
