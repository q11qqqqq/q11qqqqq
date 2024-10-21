<!DOCTYPE html>
<head>
<html lang="en">
    <meta charset="UTF-8">
    <meat hettp-equiv="X-Ua-Compatible" content="IE=edge"> 
    <meta name="viewport" content="width=device-width,intital-scale=1.0">
</head>  
    
<body>
<div id="app">
<ul v-for="(item,index) in list" :key="item.id">
   <li>{{item.username}}</li>
   <li>{{item.id}}</li>
   <li>{{item.price}}</li>

</ul>
<div>
    <input type="text" v-model="words" id="inp" key="ietm.id">
    <button>搜索一下</button>
</div>

</div>
 <script src="https://cdn.jsdelivr.net/npm/vue@2.7.16/dist/vue.js"></script>
 <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
 <script>

   const app = new Vue(
    {
        el: '#app',
        data: {
            username:'',
           gender:'',
           price:'',
           list:[],
           words:'',
           sex:'男'

           
            
        },
      async   created() {
            const res = await axios.get('http://127.0.0.1:4523/m1/5309393-4978987-default/use/?id=1111&name&price',{
                params:{
                    userid:'小白'
                }
            })
            console.log(res)
           this.list = res.data.data 
           console.log(this.list)
       
        }
        // mounted(){
        //     console.log(querySelector('#inp'))
        //     document.querySelector('#inp').focus()
        // }
    }
   )
</script>
</body>
</html>
