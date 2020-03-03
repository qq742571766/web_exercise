<template>
	<view>
		{{opName}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				opName: ""
			}
		},
		methods: {
			getParam(data) {
				console.log("1211231231313");
				let url = '';
				for (const k in data) {
					let value = data[k] !== undefined ? data[k] : '';
					url += '&' + k + '=' + encodeURIComponent(value)
				}
				return url ? url.substring(1) : '9999'
			}
		},
		onLoad: function (option) { //option为object类型，会序列化上个页面传递的参数

			console.log(option.type); //打印出上个页面传递的参数。
			console.log(option.name); //打印出上个页面传递的参数。
			this.opName = option.name;

		},
		onReady() {

			let param = {
				type: 1,
				name: 'YanGo'
			};

			let pars = this.getParam(param);
			console.log(pars)
		}
	}
</script>

<style>

</style>
