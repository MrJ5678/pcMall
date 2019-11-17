<template>
  <section class="m-istyle">
    <dl @mouseover="over">
      <dt>有格调</dt>
      <dd :class="{active:kind==='all'}" kind="all" keyword="景点">全部</dd>
      <dd :class="{active:kind==='part'}" kind="part" keyword="美食">约会聚餐</dd>
      <dd :class="{active:kind==='spa'}" kind="spa" keyword="丽人">丽人SPA</dd>
      <dd :class="{active:kind==='movie'}" kind="movie" keyword="电影">电影演出</dd>
      <dd :class="{active:kind==='travel'}" kind="travel" keyword="旅游">品质出游</dd>
    </dl>
    <ul class="ibody">
      <li v-for="item in cur" :key="item.title">
        <el-card :body-style="{ padding: '0px' }" shadow="never">
          <img :src="item.img" class="image" />
          <ul class="cbody">
            <li class="title">{{ item.title }}</li>
            <li class="pos">
              <span>{{ item.pos }}</span>
            </li>
            <li class="price">
              ￥
              <em>{{ item.price }}</em>
              <span>/起</span>
            </li>
          </ul>
        </el-card>
      </li>
    </ul>
  </section>
</template>
<script>
export default {
  data: () => {
    return {
      kind: "all",
      list: {
        all: [
          {
            title: "好利来（磁器口店）",
            img: "//p0.meituan.net/xianfu/0dff28633d42242f9d844de6f36078fd7275.jpeg@watermark=0|736w_416h_1e_1c",
            pos: "清甜云朵1个，约15厘米，圆形",
            price: "198"
          },
          {
            title: "幸福西饼生日蛋糕（西直门店）",
            img: '//p0.meituan.net/msmerchant/0a56a205c9a62ac5df50900dc412b2b01651570.jpg@736w_416h_1e_1c',
            pos: "鲜芒九方1个，约560克，方形，美味下午茶",
            price: "298"
          },
          {
            title: "CAKE BOSS 蛋糕老板（崇文门国瑞城店）",
            img: '//p0.meituan.net/msmerchant/ce99705ba3ed37e308f0facf413d4956624846.jpg@736w_416h_1e_1c',
            pos: "粉红心羽生日蛋糕1个，约7英寸，圆形",
            price: "198"
          }
        ],
        part: [{
            title: "好利来（磁器口店）",
            img: "//p0.meituan.net/xianfu/0dff28633d42242f9d844de6f36078fd7275.jpeg@watermark=0|736w_416h_1e_1c",
            pos: "清甜云朵1个，约15厘米，圆形",
            price: "198"
          },
          {
            title: "幸福西饼生日蛋糕（西直门店）",
            img: '//p0.meituan.net/msmerchant/0a56a205c9a62ac5df50900dc412b2b01651570.jpg@736w_416h_1e_1c',
            pos: "鲜芒九方1个，约560克，方形，美味下午茶",
            price: "298"
          },
          {
            title: "CAKE BOSS 蛋糕老板（崇文门国瑞城店）",
            img: '//p0.meituan.net/msmerchant/ce99705ba3ed37e308f0facf413d4956624846.jpg@736w_416h_1e_1c',
            pos: "粉红心羽生日蛋糕1个，约7英寸，圆形",
            price: "198"
          }],
        spa: [{
            title: "好利来（磁器口店）",
            img: "//p0.meituan.net/xianfu/0dff28633d42242f9d844de6f36078fd7275.jpeg@watermark=0|736w_416h_1e_1c",
            pos: "清甜云朵1个，约15厘米，圆形",
            price: "198"
          },
          {
            title: "幸福西饼生日蛋糕（西直门店）",
            img: '//p0.meituan.net/msmerchant/0a56a205c9a62ac5df50900dc412b2b01651570.jpg@736w_416h_1e_1c',
            pos: "鲜芒九方1个，约560克，方形，美味下午茶",
            price: "298"
          },
          {
            title: "CAKE BOSS 蛋糕老板（崇文门国瑞城店）",
            img: '//p0.meituan.net/msmerchant/ce99705ba3ed37e308f0facf413d4956624846.jpg@736w_416h_1e_1c',
            pos: "粉红心羽生日蛋糕1个，约7英寸，圆形",
            price: "198"
          }],
        movie: [{
            title: "好利来（磁器口店）",
            img: "//p0.meituan.net/xianfu/0dff28633d42242f9d844de6f36078fd7275.jpeg@watermark=0|736w_416h_1e_1c",
            pos: "清甜云朵1个，约15厘米，圆形",
            price: "198"
          },
          {
            title: "幸福西饼生日蛋糕（西直门店）",
            img: '//p0.meituan.net/msmerchant/0a56a205c9a62ac5df50900dc412b2b01651570.jpg@736w_416h_1e_1c',
            pos: "鲜芒九方1个，约560克，方形，美味下午茶",
            price: "298"
          },
          {
            title: "CAKE BOSS 蛋糕老板（崇文门国瑞城店）",
            img: '//p0.meituan.net/msmerchant/ce99705ba3ed37e308f0facf413d4956624846.jpg@736w_416h_1e_1c',
            pos: "粉红心羽生日蛋糕1个，约7英寸，圆形",
            price: "198"
          }],
        travel: [{
            title: "好利来（磁器口店）",
            img: "//p0.meituan.net/xianfu/0dff28633d42242f9d844de6f36078fd7275.jpeg@watermark=0|736w_416h_1e_1c",
            pos: "清甜云朵1个，约15厘米，圆形",
            price: "198"
          },
          {
            title: "幸福西饼生日蛋糕（西直门店）",
            img: '//p0.meituan.net/msmerchant/0a56a205c9a62ac5df50900dc412b2b01651570.jpg@736w_416h_1e_1c',
            pos: "鲜芒九方1个，约560克，方形，美味下午茶",
            price: "298"
          },
          {
            title: "CAKE BOSS 蛋糕老板（崇文门国瑞城店）",
            img: '//p0.meituan.net/msmerchant/ce99705ba3ed37e308f0facf413d4956624846.jpg@736w_416h_1e_1c',
            pos: "粉红心羽生日蛋糕1个，约7英寸，圆形",
            price: "198"
          }]
      }
    };
  },
  computed: {
    cur() {
      return this.list[this.kind];
    }
  },
  methods: {
    async over(e) {
      let dom = e.target;
      let tag = dom.tagName.toLowerCase();
      if (tag === "dd") {
        this.kind = dom.getAttribute("kind");
        let keyword = dom.getAttribute("keyword");
        console.log(this.kind, keyword);
      }
    }
  }
};
</script>
<style lang="scss">
@import "@/assets/css/index/artistic.scss";
</style>
