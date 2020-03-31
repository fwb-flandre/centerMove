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

在对应的 div 或 img 上添加 v-center="move"，然后在 move 函数中获取的 x 和 y 为当前鼠标位置
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
前三个参数必填

解释 $moveCenter 中第四个参数的属性（均为可选项）

xZoom:控制 x 轴上移动的幅度

yZoom:控制 y 轴上移动的幅度

xOffset:初始状态 x 轴偏移量

yOffset:初始状态 y 轴偏移量

during:每一次移动的持续时间（非线性移动）（单位为毫秒）

time:移动的开始时间（单位为毫秒）
