<script lang="ts" setup>
import donate_alipay from '~/assets/donate_alipay.png'
import donate_qq from '~/assets/donate_qq.png'
import donate_wechat from '~/assets/donate_wechat.png'

definePageMeta({
	name: '支持 & 赞助'
})
</script>

<template>
	<Subpage>
		<n-tabs animated justify-content="center" type="segment">
			<n-tab-pane name="QQ">
				<n-flex justify="center">
					<n-image :src="donate_qq" class="[&>img]:w-full"/>
				</n-flex>
			</n-tab-pane>

			<n-tab-pane name="微信">
				<n-flex justify="center">
					<n-image :src="donate_wechat" class="[&>img]:w-full"/>
				</n-flex>
			</n-tab-pane>

			<n-tab-pane name="支付宝">
				<n-flex justify="center">
					<n-image :src="donate_alipay" class="[&>img]:w-full"/>
				</n-flex>
			</n-tab-pane>
		</n-tabs>
	</Subpage>
</template>