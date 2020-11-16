<template>
	<div class="home">
		<div class="menu-list">
			<a-menu
				:default-selected-keys="['1']"
				:default-open-keys="['sub1']"
				mode="inline"
				theme="dark"
				:inline-collapsed="collapsed"
			>
				<a-menu-item key="1">
					<a-icon type="pie-chart" />
					<span>Option 1</span>
				</a-menu-item>
				<a-menu-item key="2">
					<a-icon type="desktop" />
					<span>Option 2</span>
				</a-menu-item>
				<a-menu-item key="3">
					<a-icon type="inbox" />
					<span>Option 3</span>
				</a-menu-item>
				<a-sub-menu key="sub1">
					<span slot="title">
						<a-icon type="mail" /><span>Navigation One</span>
					</span>
					<a-menu-item key="5">
						Option 5
					</a-menu-item>
					<a-menu-item key="6">
						Option 6
					</a-menu-item>
					<a-menu-item key="7">
						Option 7
					</a-menu-item>
					<a-menu-item key="8">
						Option 8
					</a-menu-item>
				</a-sub-menu>
				<a-sub-menu key="sub2">
					<span slot="title">
						<a-icon type="appstore" /><span>Navigation Two</span>
					</span>
					<a-menu-item key="9">
						Option 9
					</a-menu-item>
					<a-menu-item key="10">
						Option 10
					</a-menu-item>
					<a-sub-menu
						key="sub3"
						title="Submenu"
					>
						<a-menu-item key="11">
							Option 11
						</a-menu-item>
						<a-menu-item key="12">
							Option 12
						</a-menu-item>
					</a-sub-menu>
				</a-sub-menu>
			</a-menu>
		</div>
		<div :class="{'main-app': true, 'menu': collapsed}">
			<div class="main-header">
				<div class="left">
					<!-- 菜单按钮 -->
					<a-button
						type="primary"
						@click="toggleCollapsed"
					>
						<a-icon :type="collapsed ? 'menu-unfold' : 'menu-fold'" />
					</a-button>
					<!-- 面包屑 -->
					<div class="bread-crumb">
						<a-breadcrumb>
							<a-breadcrumb-item>首页</a-breadcrumb-item>
							<a-breadcrumb-item><a href="">API 1</a></a-breadcrumb-item>
							<a-breadcrumb-item>API 2</a-breadcrumb-item>
						</a-breadcrumb>
					</div>
				</div>
				<!-- 用户信息 -->
				<div class="user-info">
					<a-dropdown>
						<a
							class="ant-dropdown-link"
							@click="e => e.preventDefault()"
						>
							欢迎 <span> {{username}}</span>
							<a-icon type="down" />
						</a>
						<a-menu slot="overlay">
							<a-menu-item>
								<span @click="logout">退出登录</span>
							</a-menu-item>
						</a-menu>
					</a-dropdown>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			collapsed: false,
			username: "xxx",
		};
	},
	methods: {
		toggleCollapsed() {
			this.collapsed = !this.collapsed;
		},
		logout() {
			alert("退出等宽列")
		}
	},
};
</script>
<style lang="less">
@import url("~@/assets/css/home.less");
</style>
