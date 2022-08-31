<template>
	<view class="login">
		<view class="inputs">
			<view class="example">
				<!-- 基础表单校验 -->
				<uni-forms ref="valiForm" :rules="rules" :modelValue="valiFormData">
					<uni-forms-item name="phone">
						<input class="uni-input" type="tel" v-model="valiFormData.phone"
							placeholder="手机号" />
					</uni-forms-item>

					<uni-forms-item name="code">
						<view class="icode-dja">
							<input class="uni-input" style="width: 260px;" type="code"
								v-model="valiFormData.code" placeholder="验证码" />
							<button class="button1" @click="code()" v-if="type == 1">获取验证码</button>
							<button class="button1" v-if="type == 2" disabled="disabled">{{ sencod }}秒</button>
						</view>
					</uni-forms-item>

					<uni-forms-item name="pwd">
						<input class="uni-input" password type="safe-password" v-model="valiFormData.pwd"
							placeholder="密码" />
					</uni-forms-item>

					<uni-forms-item name="confirm_pwd">
						<input class="uni-input" password type="safe-password" v-model="valiFormData.confirm_pwd"
							placeholder="确认密码" />
					</uni-forms-item>
				</uni-forms>
				<button type="primary" style="margin-top: 45px;" @click="submit('valiForm')">注册</button>

				<view class="bootear">
					<view class="register" @click="url(1)">
						去登录
					</view>
					<view class="zhao" @click="url(2)">
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
				//type为1显示获取验证码 2倒计时
				type: 1,
				//倒计时
				sencod: 60,
				valiFormData: {
					phone: '',
					pwd: '',
					code: '',
					confirm_pwd: ''
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
							errorMessage: '密码不能为空'
						}]
					},
					code: {
						rules: [{
							required: true,
							errorMessage: '验证码不能为空'
						}]
					},
					confirm_pwd: {
						rules: [{
							required: true,
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
		mounted() {

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

			code() {
				//获取验证码 type状态修改为2
				this.type = 2;

				//触发倒计时
				this.timer = setInterval(() => {
					console.log(this.sencod--)
					if (this.sencod == 0) {
						this.type = 1;
					}
				}, 1000);
			},
			url(type) {
				
			}
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

	.bootear {
		text-align: center;
		position: absolute;
		bottom: 50px;
	}

	.bootear view {
		float: left;
	}

	.bootear .zhao {
		margin-left: 200px;
	}

	.button1 {
		width: 100px;
		font-size: 12px;
		float: left;
		margin-top: 20px;
		background-color: aquamarine;
		height: 40px;
		line-height: 40px;
	}

	.icode-dja input {
		float: left;
	}
</style>
