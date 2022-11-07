<template>
	<view class="content">
		<u-swiper class="swiper" :height='300' :list="list2" keyName="image" :autoplay="true" circular :radius='0'>
		</u-swiper>
		<view class="attendanceUserInfo">
			<view class="top">
				<view class="left">
					<view class="name">
						<view class="label" @click="click">
							就诊人姓名
						</view>
						<u-icon name="reload" color="#2979ff" size="52"></u-icon>
					</view>
					<view class="cardNumber">就诊卡号:87232172381728</view>
				</view>
				<view class="right">
					<bt<img class="QrCodeImg" src="../../static/QRcode.png" >
					<view class="label">出示就诊码</view>
				</view>
			</view>
			<view class="bottom">
				<view class="bottomItem">
					<img class='image' src="../../static/registrationRecord.png">
					<view>挂号记录</view>
				</view>
				<view class="bottomItem">
					<img class='image' src="../../static/addAttendanceUser.png">
					<view>添加就诊人</view>
				</view>
			</view>
		</view>
		<view class="outpatientService">
			<view class="label">门诊服务</view>
			<view class="itemList">
				<u-grid :border="false" col="4" @click="click">
					<u-grid-item v-for="(baseListItem,baseListIndex) in baseList" :key="baseListIndex">
						<img class="iconImage" :src="baseListItem.url"
							style="	width: 100rpx;height: 100rpx;display: flex;justify-content: center;align-items: center;">
						<text class="grid-text">{{baseListItem.title}}</text>
					</u-grid-item>
				</u-grid>
			</view>
		</view>
		<view class="patientService">
			<view class="label">信息服务</view>
			<view class="itemList">
				<u-grid :border="false" col="4" @click="click">
					<u-grid-item v-for="(baseListItem,baseListIndex) in baseList1" :key="baseListIndex">
						<img class="iconImage" :src="baseListItem.url"
							style="	width: 100rpx;height: 100rpx;display: flex;justify-content: center;align-items: center;">
						<text class="grid-text">{{baseListItem.title}}</text>
					</u-grid-item>
				</u-grid>
			</view>
		</view>
		<view class="reportSearch">
			<view class="label">报告查询</view>
			<view class="itemList">
				<u-grid :border="false" col="4" @click="click">
					<u-grid-item v-for="(baseListItem,baseListIndex) in baseList2" :key="baseListIndex">
						<img class="iconImage" :src="baseListItem.url"
							style="	width: 100rpx;height: 100rpx;display: flex;justify-content: center;align-items: center;">
						<text class="grid-text">{{baseListItem.title}}</text>
					</u-grid-item>
				</u-grid>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list2: [{
					image: '../../static/OIP-C.png',
				}, {
					image: '../../static/R-C.png',
				}, {
					image: 'https://s3.bmp.ovh/imgs/2022/08/02/6ec2e316251a8ff9.png',
				}],
				baseList: [{
					url: '../../static/appointmentRegister.png',
					title: '预约挂号'
				}, {
					url: '../../static/nucleicAcidTesting.png',
					title: '核酸检测'
				}, {
					url: '../../static/prescription.png',
					title: '处方查询'
				}, {
					url: '../../static/ONE.png',
					title: '个人中心'
				}],
				baseList1: [{
					url: '../../static/informationSearch.png',
					title: '信息查询'
				}, {
					url: '../../static/hospitalListing.png',
					title: '满意度调查'
				}, {
					url: '../../static/rechargeRecord.png',
					title: '在线咨询'
				},
				{
					url: '../../static/smartLeadingExamining.png',
					title: '智能引导'
				}],
				baseList2: [{
					url: '../../static/inspectionReport.png',
					title: '就诊记录'
				}, {
					url: '../../static/surveyReport.png',
					title: '检验报告'
				}, {
					url: '../../static/nucleicAcidReport.png',
					title: '核酸报告'
				}, ]
			}
		},
		onLoad() {

		},
		methods: {
			chick(){
				this.$router.replace('../login')
			}
		}
	}
</script>
<style>
	page {
		width: 100%;
		height: 100%;
		background-color: #F7F7F7;
	}
</style>
<style scoped lang="scss">
	.content {
		padding: 20rpx;
		background-color: #F7F7F7;

		.attendanceUserInfo {
			margin-top: 20rpx;
			background-color: #FFFFFF;
			border-top: 35rpx solid #78C0EB;
			border-bottom: 10rpx solid #78C0EB;
			border-radius: 10rpx;

			.top {
				display: flex;
				justify-content: space-between;
				padding: 10rpx 60rpx;
				border-bottom: 1px dashed #D3D3D3;

				.left {
					display: flex;
					flex-direction: column;
					justify-content: space-between;
					color: #706F6F;

					.name {
						display: flex;
						font-size: 40rpx;
						letter-spacing: 4rpx;
						font-weight: bold;

						.label {
							color: #454545;
							margin-right: 10rpx;
						}
					}

					.balance {
						display: flex;
						font-size: 33rpx;

						.money {
							color: #4095D2;
							letter-spacing: 4rpx;
						}
					}
				}

				.right {
					display: flex;
					flex-direction: column;
					align-items: center;
					justify-content: center;
					font-size: 20rpx;
					letter-spacing: 2rpx;

					.label {
						margin-top: 10rpx;
					}

					.QrCodeImg {
						width: 84rpx;
						height: 84rpx;
					}
				}
			}

			.bottom {
				display: flex;
				justify-content: space-between;
				padding: 20rpx 0;

				.bottomItem {
					display: flex;
					flex: 1;
					justify-content: center;
					align-items: center;
					font-size: 25rpx;
					color: #656565;

					.image {
						width: 35rpx;
						height: 35rpx;
						margin-right: 30rpx;
					}
				}

				.bottomItem:first-child {
					border-right: 1px solid #78C0EB;
				}
			}
		}

		.outpatientService,
		.patientService,
		.reportSearch {
			margin-top: 20rpx;

			.itemList {
				margin-top: 20rpx;
				background-color: #FFFFFF;
				padding: 0rpx 20rpx 30rpx;

				/deep/.u-grid-item {
					margin-top: 30rpx;
				}

				.grid-text {
					font-size: 28rpx;
					color: #909399;

				}
			}
		}
	}
</style>
