<template>
	<div id="showPic" v-if='show'>
		<img :src='src'>
		<div class="close" @click='close'>+</div>
	</div>
</template>

<script>
	export default{
		data(){
			return{
				src:'',
				show:false
			}
		},
		methods:{
			close:function(){
				this.$data.show=false;
				
			}
		},
		watch:{
			show:function(val,oldVal){
				if(val===true){
					document.body.style.overflow='hidden';
				}else{
					document.body.style.overflow='auto';
				}
			}
		}
	}
</script>

<style scoped lang='scss'>
	#showPic{
		position: fixed;
		top: 0px;
		left:0;
		width: 100%;
		height: 100%;
		background-color: rgba(0,0,0,.8);
		overflow: auto;
		z-index: 999;
		padding: 30px;
		box-sizing: border-box;
		text-align:center;
		img{
			position: relative;
			top:0;
			left: 0;
			right: 0;
			bottom: 0;
			max-width: 200%;
			vertical-align: middle;
		}
		.close{
			color: #fff;
			position: fixed;
			top: -15px;
			right: 0;
			font-size: 40px;
			margin-right: 2px;
			transform: rotate(45deg);
		}
	}
</style>