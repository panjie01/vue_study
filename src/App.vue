<template>
  <div id="app">
        <p>{{ message }}</p>
        <p>{{detail()}}</p> 
        <a :href='url'>联系我们 </a>
        <p>{{info}}</p> <!-- 实现双向数据绑定 -->
        <div>
            <input type="text" v-model="info" />
            <button v-on:click="handlerClick">添加</button>
            <!-- <button @click="handlerClick">添加</button> -->
        </div>
        <ul>
            <todo-item v-for="key in list"  :key="key">
               <span slot="st" slot-scope="props" :style=" {fontSize: '20px',color:props.checked?'red':'blue'} ">{{key}}</span>
               
            </todo-item>

            <!-- <todo-item v-for="key in list" :item='key' :key="key"></todo-item> -->
        </ul>

        <template v-if="info">
          <h1>为梦想加油</h1>
          <p>学的不仅是技术，更是梦想！</p>
          <p>哈哈哈，打字辛苦啊！！！</p>
        </template>

    </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'app',
  data() {
      return {
            message: 'Hello World!',
            info:'',
            list:[],
            url: 'https://www.baidu.com'
            // item2:'123'
             }
        },
  methods:{
            handlerClick() {
                if(this.info=='' || this.info==null){
                    alert('info can not be null')
                    return
                }
                console.log(this.info)
                this.list.push(this.info)
                this.info=''
            },
            detail(){
              return  "学的不仅是技术，更是梦想!";
            } 
        },
  components: {
    TodoItem
  }      
}





</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
