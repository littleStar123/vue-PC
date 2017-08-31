<template>
	<div>
		<ul>
			<li>{{msg}}</li>
			<li>{{childMsg}}</li>
			<li>
				<div @click="toParent">click To parent</div>
			</li>			
		</ul>
	</div>
</template>
<script>
export default {
	name:"child",
	components: {
		
	},
	data () {
	    return {
	      msg: 'this is child',
	      data:"from child"
	    }
	},
	props:{
		childMsg: {
	        type: String,
	        default: "null" //这样可以指定默认的值
   		}
	},
	methods:{
		toParent(){
			this.$emit('upup',this.data); //主动触发upup方法，'hehe'为向父组件传递的数据
		}
	}
}
</script>

<style scoped>
li{
	list-style: none;
}
ul{
	background: #CCCCCC;
}
</style>