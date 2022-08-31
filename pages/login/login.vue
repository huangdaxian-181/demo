<template>
	<view class="login">
		<view class="logo">
			<img src="static/shi/9a9fd90648e54580023a1a0317c0f95e.jpeg" alt="logo图片">
		</view>

		<view class="inputs">
			<view class="example">
				<!-- 基础表单校验 -->
				<uni-forms ref="valiForm" :rules="rules" :modelValue="valiFormData">
					<uni-forms-item name="phone">
						<input class="uni-input" type="tel" @focus="height" v-model="valiFormData.phone"
							placeholder="手机号" />
					</uni-forms-item>
					
					<uni-forms-item name="pwd">
						<input class="uni-input" password type="safe-password" v-model="valiFormData.pwd" placeholder="密码" />
					</uni-forms-item>
				</uni-forms>
				<button type="primary" style="margin-top: 45px;" @click="submit('valiForm')">登录</button>
				
				<view class="bootear">
					<view class="register">
						注册账户
					</view>
					<view class="zhao">
						找回密码
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		components: {},
		data() {
			return {
				title: 'Hello',
				valiFormData: {
					phone: '',
					pwd: '',
					introduction: '',
				},
				rules: {
					phone: {
						rules: [{
							required: true,
							errorMessage: '手机号不能为空'
						}]
					},
					pwd: {
						rules: [{
							required: true,
							format: 'number',
							errorMessage: '手机号不能为空'
						}, {
							errorMessage: '密码不能为空'
						}]
					}
				},
			}
		},
		onLoad() {

		},
		onReady() {

		},
		computed: {

		},
		methods: {
			onKeyInput: function(event) {
				this.inputValue = event.target.value
			},
			replaceInput: function(event) {
				var value = event.target.value;
				if (value === '11') {
					this.changeValue = '2';
				}
			},
			hideKeyboard: function(event) {
				if (event.target.value === '123') {
					uni.hideKeyboard();
				}
			},
			onClickItem(e) {
				console.log(e);
				this.current = e.currentIndex
			},
			add() {
				this.dynamicLists.push({
					label: '域名',
					rules: [{
						'required': true,
						errorMessage: '域名项必填'
					}],
					id: Date.now()
				})
			},
			del(id) {
				let index = this.dynamicLists.findIndex(v => v.id === id)
				this.dynamicLists.splice(index, 1)
			},
			submit(ref) {
				this.$refs[ref].validate().then(res => {
					console.log('success', res);
					uni.showToast({
						title: `校验通过`
					})
				}).catch(err => {
					console.log('err', err);
				})
			},
		}
	}
</script>

<style lang="scss">
	.login {
		border: 1px solid #fff;
	}

	.logo {
		border: 1px solid #fff;
		width: 100%;
		margin-top: 60px;
		text-align: center;
	}

	.logo img {
		width: 25%;
		height: 25%;
	}

	.inputs {
		border: 1px solid #fff;
	}

	.example {
		padding: 25px;
		background-color: #fff;
	}

	.segmented-control {
		margin-bottom: 15px;
	}

	.button-group {
		margin-top: 15px;
		display: flex;
		justify-content: space-around;
	}

	.form-item {
		display: flex;
		align-items: center;
	}

	.button {
		display: flex;
		align-items: center;
		height: 35px;
		margin-left: 10px;
	}

	.uni-input {
		border-bottom: 1px solid #E0E0E0;
		height: 60px;
	}
	.bootear{
		text-align: center;
		position: absolute;
		bottom: 50px;
	}
	
	.bootear view{
		float: left;
	}
	.bootear .zhao{
		margin-left: 200px;
	}
</style>
