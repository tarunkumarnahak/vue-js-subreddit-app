<template>
	<div class="Subreddit">
		<a :href="makeurl(item.data.permalink)" :style="makeImage(item.data.thumbnail)" target="_blank" class="thumbnail"></a>
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
			}
		}
	}
</script>
<style scoped>
	.subreddit{
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
	</style>
