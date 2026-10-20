<script lang="ts" setup>
import { darkTheme, dateZhCN, lightTheme, useOsTheme, zhCN } from 'naive-ui'
import avatar from '~/assets/avatar.png'

const osTheme = useOsTheme()
const theme = computed(() => {
	if (osTheme.value === 'dark') {
		return darkTheme
	}

	return lightTheme
})

useHead({
	link: [
		{
			rel: 'icon',
			href: avatar
		}
	]
})
</script>

<template>
	<NuxtLayout>
		<NuxtLoadingIndicator/>

		<n-config-provider :date-locale="dateZhCN" :locale="zhCN" :theme="theme">
			<n-dialog-provider>
				<n-loading-bar-provider>
					<n-message-provider>
						<n-notification-provider>
							<n-layout position="absolute">
								<n-layout-content class="container mx-auto">
									<n-element class="<sm:(px-2) pt-10 pb-20">
										<NuxtPage/>
									</n-element>
								</n-layout-content>

								<n-layout-footer class="p-2" position="absolute">
									<n-flex :size='0' align="center" justify='center'>
										<n-text>&copy; 2024 - {{ new Date().getFullYear() }}</n-text>
										<n-divider vertical/>
										<n-text>开发:&nbsp;</n-text>
										<n-button href="https://zhazha120.cn" tag="a" text>渣渣120</n-button>
									</n-flex>
								</n-layout-footer>
							</n-layout>
						</n-notification-provider>
					</n-message-provider>
				</n-loading-bar-provider>
			</n-dialog-provider>
		</n-config-provider>
	</NuxtLayout>
</template>

<style>
* {
	@apply box-border;
}

.page-enter-active,
.page-leave-active {
	@apply transition-(all duration-300) ease-in-out;
}

.page-enter-from,
.page-leave-to {
	@apply opacity-0 blur;
}
</style>