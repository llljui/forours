<template>
  <div class="home">
    <img class="header" src="http://qiniu.dotregion.com/52.jpg" alt="">
	<div class="huaban" :style="{heigt:autoheight }">
		<img :src="huabansrc" alt="loading" :style="{width:item.w+'px',top:item.top+'px',left:item.l+'px'}" v-for="(item,index) in hlist" :key="index">
	</div>
	<div class="content">
		<div class="flex-row flex-y-center flex-x-center">
			<div class="flex-grow-0 abba">
				此处为时间线
				<ourtime></ourtime>
			</div>
		</div>
		<div class="flex-row flex-y-center trval flex-x-center">
			<div class="flex-grow-1">吃</div>
			<div class="flex-grow-1">喝</div>
			<div class="flex-grow-1">玩</div>
			<div class="flex-grow-1">乐</div>
		</div>
	</div>
	<footer class="txt-center">
		<a class="beian" href="http://beian.miit.gov.cn/">ICP证：{{beian}}</a>
	</footer>
  </div>
</template>

<script>
import ourtime from '@/components/ourtime.vue';
export default {
  name: 'Home',
  components: {
    ourtime
  },
  data(){
	  return{
		  beian:'浙ICP备17012690号-2',
		  autoheight:'',
		  huabansrc:'http://qiniu.dotregion.com/huaban.png',
		  hlist:[],
		  down:null
	  }
  },
  created() {
	let self = this;
  	window.onresize = function(val){
		if(window.screen.availWidth <= 1200){self.autoheight = (window.screen.availWidth*.6) +'px';return}
		self.autoheight = (window.screen.availWidth*.6) +'px';
	}
	function random(min, max){
	    return min + Math.floor(Math.random() * (max - min + 1));
	}
	let hlist = [];
	// 这里有三个状态  prerender，visible 和 hidden 
	let pageVisibleStatus = document.visibilityState; 
	
	// 监听页面状态
	document.addEventListener('visibilitychange', function() {
	  // 页面状态变化为不可见时触发 
	  if (document.visibilityState == 'hidden') {
		   console.log('hide');
		  window.clearInterval(self.down);
	  } 
	  // 页面状态变化为可见时触发 
	  if (document.visibilityState == 'visible') {
		  console.log('visible');
		  self.down = setInterval(()=>{
		  	for(let x = 0;x<30;x++){
		  		hlist.push({w:random(0,10),l:random(0,1200),s:1,top:random(-20,-380)})
		  	}
		  	self.hlist = hlist;
		  },3500)
	    } 
	  }
	);
	
  }
}
</script>
<style lang="less" scoped>
	@keyframes down{
		0%{
			opacity: 1;
		}
		10%{
			transform: translateX(0px) rotateY(0deg) translateY(0px);
			opacity: 1;
		}
		100%{
			transform: translateX(300px) rotateY(-7200deg) translateY(600px);
			opacity: 0;
		}
	}
	.home{
		min-width: 1200px;
		position: relative;
		width: 100vw;
		.header{
			width: 100%;
		}
		.huaban{
			position: absolute;
			width: 100%;
			min-width: 1200px;
			top: 0;
			left: 0;
			z-index: 2;
			img{
				animation: down 9s 1;
				opacity: 0;
				width: 100%;
				position: absolute;
			}
		}
		footer{
			padding: 20px 0;
			border-top: 1px solid #ddd;
			.beian{
				font-size: 14px;
				color: #2b2b2b;
				font-weight: bold;
			}
		}
		.content{
			.abba{
				height: 160px;
				padding: 20px 0;
			}
			.trval{
				width: 1000px;
				margin: 10px auto;
				>div{
					height: 180px;
					border: 1px solid #ddd;
					margin: 0 10px;
					border-radius: 6px;
				}
			}
		}
	}
</style>
