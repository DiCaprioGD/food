<template>
  <div class="hello">
    <div>
      吃什么: {{ msg }}
    </div>
    <a-radio-group v-model="value">
      <a-radio :value="1">
        点菜
      </a-radio>
      <a-radio :value="2">
        不点菜
      </a-radio>
    </a-radio-group>
    <a-button type="primary" @click="random">
      点击出菜
    </a-button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      arr: ["喝粥","斩鸭子","香锅","煎饺锅贴","酸菜鱼","地锅鸡（大盘鸡）","粉","肯德基","麻辣烫","蛋包饭","米线","黄焖鸡","炸鸡（鸡排，鸡柳）","叉烧饭","木桶饭", "热干面", "手撕烤鸭", "华莱士", "炒饭", "椒麻鸡", "花甲", "紫燕", "酸菜鱼"],
      arr2: ["西红柿炒鸡蛋","酸辣土豆丝","肉末茄子","干锅花菜","干锅包菜","地三鲜","韭黄炒蛋","韭菜炒豆芽","西兰花","四季豆","蒜泥菠菜","麻婆豆腐"],
      arr3: ["梅菜扣肉","红烧排骨","糖醋里脊","青椒肉丝","烤鸭","啤酒鸭","蒸腊肉","小炒鸡","辣子鸡","腐竹炒肉","鱼香肉丝","腊肉炒笋尖","小炒黄牛肉","黄瓜炒火腿","腊肠"],
      msg: '',
      value: 1,
    }
  },
  methods: {
    random() {
      if (this.value === 1) {
        this.msg = `素菜: ${this.arr2[this.randomNum(this.arr2)]}和${this.arr2[this.randomNum(this.arr2)]} 荤菜: ${this.arr3[this.randomNum(this.arr3)]}和${this.arr3[this.randomNum(this.arr3)]}`
      } else {
        this.msg = this.arr[this.randomNum(this.arr)]
      }
    },
    randomNum(len) {
      return Math.floor( Math.random() * len.length )
    }
  }
}
</script>

<style scoped>

</style>
