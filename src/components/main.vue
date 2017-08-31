<template>
	<div>
		<child @upup="change" :child-msg="data"></child>
		<div>
		    {{childData}}
		</div>
	</div>
</template>
<script>
import child from './child.vue';
export default {
	components: {
		child
	},
	data () {
	    return {
	       	data: "from parent",
	       	childData:""
	    }
	},
	methods:{
		change(msg){
			this.childData=msg;
			this.data="parent change"
		}
	}
}
</script>

<style scoped>
</style>