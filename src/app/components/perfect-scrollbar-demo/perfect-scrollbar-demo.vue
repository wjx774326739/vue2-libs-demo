<template>
  <div>
    <div class="demo-content">
      <v-perfect-scrollbar @instanceChange="getPSInstance($event)">
        <div class="example-content">
          <p># ngx-perfect-scrollbar组件：</p>
          <p>## 说明</p>
          <p>- 这是一个基于perfect-scrollbar封装的组件，实现当组件中的内容过长，超出组件父元素的宽度和高度时，显示滚动条的功能；</p>
          <p>
            -
            使用时，需要引入模块“NgxLibsModule”或“NgxPerfectScrollbarModule”.引入“NgxLibsModule”时，可使用ngx-libs中的任何一种组件；引入“NgxPerfectScrollbarModule”时，将只能使用当前组件；
          </p>
          <p>- 使用时，直接引入相应的模块，在相应的位置使用该组件，无需再引入perfect-scrollbar的js文件和css文件；</p>

          <p>## API接口：</p>
          <p>
            ###
            ngx-perfect-scrollbar组件：限制滚动条中的内容显示区域。当滚动条内容中的区域超出滚动条外的区域限制，则出现滚动条；
          </p>
          <p>
            - [ngOptions] - Object -
            perfect-scrollbar滚动条的配置信息，具体配置见官方说明（https://github.com/utatti/perfect-scrollbar.git）;
          </p>
          <p>
            - [ngRefresh] - boolean -
            是否刷新滚动条。true表示刷新，false表示不刷新。支持双向绑定写法[(ngRefresh)]="show"；
          </p>
          <p>
            - (ngRefreshChange) - EventEmitter -
            获取当前是否正在刷新滚动条。当值为false时表示不刷新或者已经刷新完毕；
          </p>
          <p>- (instanceChange) - EventEmitter - 获取当前滚动条实例；</p>
          <p>### SCROLL_DIRECTION:滚动方向枚举类型</p>
          <p>- SCROLL_TOP - 'scrollTop' - 向top方向滚动；</p>
          <p>- SCROLL_LEFT - 'scrollLeft' - 向left方向滚动；</p>
          <p>### NgxPerfectScrollbarService：提供ngx-perfect-scrollbar组件相关功能的服务</p>
          <p>
            #### animateScrolling(instance: any, target: SCROLL_DIRECTION, value:
            number, speed?: number):void - 滚动动画,流畅地滚动组件中的内容；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- target - SCROLL_DIRECTION - 必填 - 要执行的操作;</p>
          <p>- value - number - 必填 - 滚动的距离值（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void -</p>
          <p>#### destroyPerfectScrollbar(instance: any):void - 销毁滚动条实例；</p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>##### 返回值</p>
          <p>- void -</p>
          <p>
            #### initPerfectScrollbar(el: HTMLElement, options: Object, instance?:
            any):any - 初始化滚动条；
          </p>
          <p>##### 参数</p>
          <p>- el - HTMLElement - 必填 - 要添加滚动条的html元素;</p>
          <p>- options - Object - 必填 - 滚动条配置;</p>
          <p>- instance - any - 选填 - 已经存在的滚动条实例；如果要初始化的元素已经初始化过，那么应该先将原来初始化的实例销毁;</p>
          <p>##### 返回值</p>
          <p>- any - 滚动条实例;</p>
          <p>
            #### scrollTo(instance: any, x: number, y?: number, speed?:
            number):void -
            将内容滚动到指定位置；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- x - number - 必填 - x轴方向滚动多长距离（以px为单位）;</p>
          <p>- y - number - 选填 - y轴方向滚动多长距离（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToBottom(instance: any, offset?: number, speed?:
            number):void -
            将内容滚动到底部指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- offset - number - 选填 - y轴方向偏移底部多长距离（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToElement(instance: any, qs: string, offsetX?: number,
            offsetY?: number, speed?: number):void - 滚动到指定dom元素的位置；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- qs - string - 必填 - 指定元素的选择器;</p>
          <p>- offsetX - number - 选填 - x轴偏移量（以px为单位）;</p>
          <p>- offsetY - number - 选填 - y轴偏移量（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToLeft(instance: any, offset?: number, speed?: number):void
            -
            将内容滚动到左边指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- offset - number - 选填 - x轴方向偏移左边多长距离;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToRight(instance: any, offset?: number, speed?:
            number):void -
            将内容滚动到右边指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- offset - number - 选填 - x轴方向偏移左边多长距离;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToTop(instance: any, offset?: number, speed?: number):void
            -
            将内容滚动到顶部指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- offset - number - 选填 - y轴方向偏移顶部多长的距离（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToX(instance: any, x: number, speed?: number):void -
            将内容在x轴方向滚动到指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- x - number - 必填 - x轴方向滚动多长距离（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
          <p>
            #### scrollToY(instance: any, y: number, speed?: number):void -
            将内容在y轴方向滚动到指定位置（以px为单位）；
          </p>
          <p>##### 参数</p>
          <p>- instance - any - 必填 - 滚动条实例;</p>
          <p>- y - number - 必填 - y轴方向滚动多长距离（以px为单位）;</p>
          <p>- speed - number - 选填 - 滚动速度;</p>
          <p>##### 返回值</p>
          <p>- void - ;</p>
        </div>
      </v-perfect-scrollbar>
    </div>
    <div class="demo-func">
      <button @click="goToTop()">滚动到顶部</button>
      <button @click="goToBottom()">滚动到底部</button>
      <button @click="goToLeft()">滚动到左边</button>
      <button @click="goToRight()">滚动到右边</button>
    </div>
  </div>
</template>
<script>
import { VPerfectScrollbarService } from "vue2-libs";
export default {
  name: "perfect-scrollbar-demo",
  data() {
    return {
      // 滚动条实例
      psInstance: null,
      psService: new VPerfectScrollbarService()
    };
  },
  methods: {
    getPSInstance(instance) {
      this.psInstance = instance;
    },
    goToTop() {
      this.psService.scrollToTop(this.psInstance);
    },
    goToBottom() {
      // 1000ms滚动最底部
      this.psService.scrollToBottom(this.psInstance, undefined, 1000);
    },
    goToLeft() {
      this.psService.scrollToLeft(this.psInstance);
    },
    goToRight() {
      this.psService.scrollToRight(this.psInstance);
    }
  }
};
</script>
<style lang="scss" scoped>
.demo-content {
  width: 600px;
  height: 600px;
  margin: auto;
  background-color: lightblue;
}

.example-content {
  width: 1000px;
  height: 1000px;
}
</style>
