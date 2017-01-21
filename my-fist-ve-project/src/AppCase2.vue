<template>
  <div id="app">
   <h1 v-html="title"></h1>
  
   <ul>
   	<li v-for="item in items" v-bind:class="{finished:item.isFinished}" v-on:click="toggleFinish(item)">
   		{{item.label}}
   	</li>
   </ul>
  </div>
</template>

<script>
export default {
 data:function(){
 	return {
 		title:'this is a todo list',
 		items:[
 			{
 				label:'coding',
 				isFinished:false
 			},
 			{
 				label:'walking',
 				isFinished:true
 			}
 		]
 		}
 },
 	methods:{
 			toggleFinish:function(item){
 				item.isFinished =!item.isFinished
 			}
 }
}
</script>

<style>
.finished{
	text-decoration: underline;
	color: red;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
