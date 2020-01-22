<template>
	<div class="Subreddit">
		<a :href="makeurl(item.data.permalink)" :style="makeImage(item.data.thumbnail)" target="_blank" class="thumbnail"></a>
		<div class="details">
			<a :href="makeurl(item.data.permalink)" :title="item.data.title" target="_blank" class="title">
				{{item.data.title |truncate}}
			</a>
			<br />
			<div class="stats">
				<i class="material-icons">thumbs_up_down</i>
				{{item.data.score}}
				<i class="material-icons">forum</i>
				{{item.data.num_comments}}
				
			</div>
		</div>
	</div>

</template>

<script >
	
	export default {
		name:'subreddit',
		props:['item'],
		methods: {
			makeImage:function(img){
				return 'background-image: url('+img+')';
			},
			makeurl : function(permalink) {
				return 'http://reddit.com/'+permalink;
				// body...
			},
			filter: {
				truncate: function(value){
					var length =50;
					if(value.length<=length){
						return value;
					}
					else{
						return value.substring(0,length)+'... '
					}
				}
			}
		}
	}
</script>
<style scoped>
	.Subreddit{
		display: flex;
	}
	.thumbnail{
		display: block;
		flex: 0 0 65px;
		height: 65px;
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		margin-right: 12px;
		border-radius: 5px;

	}
	.subreddit .details .title{
		font-size: 15px;
		margin-bottom: 5px;
		color: steelblue;

	}
	.subreddit .stats{
		font-size: 12px;
		margin-right: 4px;
		margin-top: 7px;
		display: inline-block;
		color: #666666;

	}
	.subreddit .stats{
		font-size: 10px;
		margin-right: 2px;
	}
	</style>
