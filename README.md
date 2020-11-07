# vuejs
1. simple.html

```
<!DOCTYPE html>
<html>
<head>
    <title>My first Vue app</title>
    <script src="https://unpkg.com/vue"></script>
</head>
<body>

<div id="app">
    {{ message }}
</div>
<script>
    var app = new Vue({
        el: '#app',
        data: {
            message: 'Hello Vue!'
        }
    })
</script>
</body>
</html>
```
output:

Hello Vue!
### Method vs Function
```
    var app = new Vue({
        el: '#app',
        data: {
        
        } ,
        mounted: function(){
          this.hello() ,    //function call
          this.addName()    //method call
        },
        methods:{
            addName(){                  //method declered
                console.log("working")
            },
            hello: function () {                 //function declared
                console.log('Hello from mixin!')
            }
        }

    })
```
### For Loop
```
<div v-for="item in items">
  {{ item.text }}
</div>
```
```
<div v-for="item in items">
  <tr v-for="t in item.color">>
    <td>{{ t.amount }}</td>
    <td>{{ t.asset }}</td>
    <td>{{ t.timestamp }}</td>>
  </tr>
</div>
```
To access the position in the array(index)
```
<div v-for="(item, index) in items">
 {{ item.text }}
</div>
```
```
<div v-for="(item, index) in items"></div>
<div v-for="(val, key) in object"></div>
<div v-for="(val, name, index) in object"></div>
```

###Event Listener
```
<button v-on:click="addName">Add</button>
<button @click="addName">Add</button>   //shorthand

<button @click.prevent="doThis"></button>       //To prevent(e.g. page reload)
<form @submit.prevent></form>

<button @click="addToCart(product)"></button>   //Arguments can be passed

<input @keyup.enter="submit">
<input @keyup.ctrl.c="onCopy">  //Call onCopy when control-c is pressed

<button v-on:click.once="doThis"></button>  <!-- the click event will be triggered at most once -->

