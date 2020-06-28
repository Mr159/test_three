<template>
  <div class="hello">
      <div class="btn-area">
       <a href="javascript:;" class="btn btn--m" @click="addCart">加入购物车</a>
      </div>
      <Modal v-bind:mdShow="mdShow" v-on:close="closeModal">
        <p slot="message">
          请先的登录,再加入购物车
        </p>
        <div slot="btnGroup">
          <a class="btn btn-m" @click="closeModal">关闭</a>
          <!-- <a href="javascript:;" class="btn btn-m" @click="closeModal">继续购物</a>
          <router-link href="javascript:;" class="btn btn-m" to="/cart" >查看购物车</router-link> -->
        </div>
      </Modal>
      <div>
        <div v-for="(item,index) in list" :key="index">
            {{item.name}}
            <img src="'./static/img/'+item.img">
        </div>
        <button @click="getData">点击我展开</button>
      </div>
      <div>
        <p>哈哈还可以</p>
        <h1>哈哈哈</h1>
        <h1>哈哈哈</h1>
        <h1>哈哈哈</h1>
        <h1>哈哈哈</h1>
        <p>上课的卢萨卡</p>
        <p>我下</p>
      </div>
      <div>
        <p>sdmlsa</p>
      </div>
  </div>
</template>

<script>
import axios from "axios"
import Modal from "./Modal"

export default {
  name: 'HelloWorld',
  components:{Modal},
  data () {
    return {
      mdShow: false,
      list:[]
    }
  },
  methods:{
    addCart(){
            this.mdShow=true
          } ,
    closeModal(){
            this.mdShow=false
          },
    getData(){
      axios.get("../../static/data.json").then(res=>{
        this.list = res.data.imgData
        console.log(res)
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
