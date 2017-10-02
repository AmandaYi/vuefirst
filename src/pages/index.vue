<template>
	<div class="content">
		<div class="content-left">
			<div class="aside" v-for="pro in productList">
				<h3>{{pro.title}}</h3>
				<template>		 
				<ul v-for="item in pro.list">
					<li><a :href="item.url">{{item.name}}</a>
						<span v-if="item.hot" class="hot">HOT</span>
					</li>
				</ul>
				<div v-if="!pro.proLast" class="hr"></div>
				</template>
							
			</div> 
		</div>


		<div class="content-right">
			<ul>
				<li class="item" v-for="item in boardList">
					 
					<div class="item-left" :class="'index-board-'+item.id">
						 
					</div>
					<div class="item-rigth">
						<h3>{{item.title}}</h3>
						<p>{{item.description}}</p>
						<button>立刻购买</button>
					</div>
					
				</li>
				 
				 
			</ul>
		</div>

	</div>
</template>
<script>
	export default {
		data: function () {
			return {
				// 产品左边列表
			 productList: {			 
    		    pc: {
		          title: 'PC产品',
		          list: [
		            {
		              name: '数据统计',
		              url: 'http://starcraft.com'
		            },
		            {
		              name: '数据预测',
		              url: 'http://warcraft.com'
		            },
		            {
		              name: '流量分析',
		              url: 'http://overwatch.com',
		              hot: true
		            },
		            {
		              name: '广告发布',
		              url: 'http://hearstone.com'
		            }
		          ]
		        },
		        app: {
		          title: '手机应用类',
		          proLast: true,
		          list: [
		            {
		              name: '91助手',
		              url: 'http://weixin.com'
		            },
		            {
		              name: '产品助手',
		              url: 'http://twitter.com',
		              hot: true
		            },
		            {
		              name: '智能地图',
		              url: 'http://maps.com'
		            },
		            {
		              name: '团队语音',
		              url: 'http://phone.com'
		            }
		          ]
		        }
		      },

		      // 右边的四个框
		       boardList: [
		        {
		          title: '开放产品',
		          description: '开放产品是一款开放产品',
		          id: 'car',
		          toKey: 'analysis',
		          saleout: false
		        },
		        {
		          title: '品牌营销',
		          description: '品牌营销帮助你的产品更好地找到定位',
		          id: 'earth',
		          toKey: 'count',
		          saleout: false
		        },
		        {
		          title: '使命必达',
		          description: '使命必达快速迭代永远保持最前端的速度',
		          id: 'loud',
		          toKey: 'forecast',
		          saleout: true
		        },
		        {
		          title: '勇攀高峰',
		          description: '帮你勇闯高峰，到达事业的顶峰',
		          id: 'hill',
		          toKey: 'publish',
		          saleout: false
		        }
		      ],
			 
		}
	}
}


</script>
<style lang="less" scoped>
.content {
	&::after{
		content:'';
		height: 0px;
		display:block;
		visibility: hidden;
		clear:both;
	}
	width:100%;
	.content-left { 
		width: 20%;
		float: left;
		
		.aside {
			width: 100%;
			h3 {
				height: 40px;
				line-height: 40px;
				text-align: center;
				background: #ddffff;
			}
			div {
				text-align:center;
				background: #deff88;
				height:30px;
				line-height: 30px;
			}
			ul {
				background: #ccdd55;
				padding: 15px 22px;
				li {
					a {
						display:inline-block;
						height: 20px;
						line-height:20px;
						background: #fff;
					}
					.hot{
						background: #f00;
						color: #fff;
					}
				}
			}
			.hr{
				height: 3px;
				background: #000;
			}
		}
	}
	.content-right {
		width: 60%;
		float: left;
		margin-left: 20px; 
		// background: #000;

		.item{
			float: left;
			margin-right: 20px;
			width: 40%;
			margin-top: 20px;

			background: #f00;
			.item-left {
				width: 100px;
				height: 100px;
				&.index-board-car{
				  background: url(../assets/images/1.png) no-repeat;
				}
				&.index-board-loud{
				  background: url(../assets/images/2.png) no-repeat;
				}
				&.index-board-earth{
				  background: url(../assets/images/3.png) no-repeat;
				}
				&.index-board-hill{
				  background: url(../assets/images/4.png) no-repeat;
				}
			}

			.item-right {
				h3 {

				}
				p {}
				button {}
			}
			&.line-last{
				margin-right: 0px;
			}
		}
		
	}

}
	
</style>