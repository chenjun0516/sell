<template>
	<div class="ratings">
		<ul>
			<li v-for="item in goods" class="menu-item">
				{{ item.text }}
				{{ item.text }}
				{{ item.text }}
				{{ item.text }}
				{{ item.text }}
				{{ item.text }}
			</li>
		</ul>
	</div>
</template>
<script type="text-ecmascript-6">
	const ERR_OK = 0;
	export default {
		props: {
			seller: {
				type: Object
			}
		},
		data () {
			return {
				goods: []
			}
		},
		created () {
			this.classMap = ['decrease', 'discount', 'special', 'invoice', 'guarantee'];

			this.$http.get('/api/ratings').then ((response) => {
				response = response.body;
				if (response.errno === ERR_OK) {
					this.goods = response.data;
				}
			})
		}
	};
</script>
<style lang="stylus" rel="stylesheet/stylus">
	.ratings
		position: absolute
		top: 174px
		bottom: 0
		left: 0
		width: 100%
		overflow:auto
</style>