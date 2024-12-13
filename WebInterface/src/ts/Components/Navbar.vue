<template>
	<b-navbar class="has-shadow is-spaced is-fixed-top">
		<template slot="brand">
			<b-navbar-item
				class="notification is-primary"
				id="ts3ab-logo"
				tag="router-link"
				:to="{ path: '/' }"
			>音乐播放器</b-navbar-item>
		</template>
		<template slot="start">
			<b-navbar-item tag="router-link" :to="{ path: '/overview' }">
				<b-icon icon="view-dashboard"></b-icon>
				<span>查看服务器运行状态</span>
			</b-navbar-item>
			<b-navbar-item tag="router-link" :to="{ path: '/bots' }">
				<b-icon icon="robot"></b-icon>
				<span>机器人列表</span>
			</b-navbar-item>
			<b-navbar-item tag="router-link" :to="{ path: '/openapi' }">
				<b-icon icon="api"></b-icon>
				<span>控制台指令</span>
			</b-navbar-item>
		</template>

		<template slot="end">
			<b-tooltip label="Visit our Project" position="is-bottom">
				<b-navbar-item tag="a" href="https://github.com/Splamy/TS3AudioBot" target="_blank">
					<b-icon icon="github-circle"></b-icon>
					<span class="is-hidden-desktop">Visit our Project</span>
				</b-navbar-item>
			</b-tooltip>
			<b-tooltip label="Site Settings" position="is-bottom">
				<b-navbar-item tag="a" @click.native="openSiteSettings()">
					<b-icon icon="cog"></b-icon>
					<span class="is-hidden-desktop">网站设置</span>
				</b-navbar-item>
			</b-tooltip>

			<b-tooltip label="Login" position="is-bottom">
				<b-navbar-item tag="router-link" :to="{ path: '/' }">
					<b-icon icon="shield-key"></b-icon>
					<span class="is-hidden-desktop">登陆</span>
				</b-navbar-item>
			</b-tooltip>
		</template>
	</b-navbar>
</template>

<script lang="ts">
import Vue from "vue";
import SiteSettingsModal from "../Modals/SiteSettingsModal.vue";

export default Vue.extend({
	data() {
		return {};
	},
	methods: {
		openSiteSettings() {
			this.$buefy.modal.open({
				parent: this,
				component: SiteSettingsModal,
				hasModalCard: false
			});
		}
	},
	components: {
		SiteSettingsModal
	}
});
</script>

<style lang="less">
#ts3ab-logo {
	margin-bottom: 0;
}
</style>
