<template>
  <div class="hello">
    <div class="container">
        <table>
            <h3>添加品牌</h3>
          <label for="">序号</label>
            <input type="text" v-model="id">
            <label for="">名字</label>
            <input type="text" v-model="name">
            <button @click="add">添加</button>
          <thead>
              <td>序号</td>
                <td>品牌</td>
                <td class="three">添加时间</td>
                <td>操作</td>
          <tbody>
            <tr v-for="(item,index) in list" :key="index">
             <td>{{item.id}}</td>
             <td>{{item.name}}</td>
             <td class="three">{{item.ctime}}</td>
             <td>
               <a href="javascript:;" @click="del(index)">删除</a>
             </td>
              </tr>
          </tbody>
          </thead>
        </table>
    </div>
 
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
   data () {
    return {
      id:"",
      name:"",
        list:[
          {
            id:1,name:"宝马",ctime:new Date()
          }, {
            id:2,name:"奥迪",ctime:new Date()
          }, {
            id:3,name:"奔驰",ctime:new Date()
          },
        ]
   };
   },
   methods:{
     add:function(){
       console.log(this.list)
       var newData ={
         id:this.id,
         name:this.name,
         ctime:new Date()
       }
       this.list.push(newData)//添加新数据
     },
      del:function(index){
        console.log(index)
        this.list.splice(index,1)
   }
   },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
a {
  color: #42b983;
  text-decoration: none;
}
*{
  margin: 0;
  padding: 0;
  margin:0 auto
}
 .hello,html,body{
   width:100%;
   height: 100%;
   background: #ccc
 }
 h3,.container{
   text-align: center;
 }
 table>thead>td{
  padding:0  20px;

 }
 thead{
   display: block;
  margin-top:20px 
 }
 table{
    width: 600px;
   height: 60px;
   display: block;
 }
 table>.three{
   padding:0 500px;
  display: block;
 }
 table>{
   width: 600px;
   height: 100%;
   display: block;
   text-align: center;
 
 }
 tbody{
    width: 80px;
   height: 100%;
  //  background: salmon;
   margin-left: -10px;
   display: flex;
   flex-direction: column
   
 }
 tbody>tr{
   width: 100%;
   height: 100%;
   display: block;
   margin-left: 10px;
 }
 tbody>tr>td{
   width: 100%;
   height: 50px;
  //  line-height: 100px;
   padding:10px 15px 0 30px;
  margin-left: 450px;

  
 }
 
 .container{
   width: 800px;
   height: 500px;
  
 }
</style>

