<script lang="ts" setup>
import '~/scripts/sakura'

import { HeartOutlined, MailOutlined, QqOutlined, UsergroupAddOutlined } from '@vicons/antd'
import avatar from '~/assets/avatar.png'
import { isMobile } from '~/shared/responsive'

const downloadableAssets = import.meta.glob<string>('~/assets/download/*', {
	eager: true,
	import: 'default',
	query: '?url'
})

const supportPageLink = useLink({
	to: {
		name: '支持 & 赞助'
	}
})
</script>

<template>
	<n-flex vertical>
		<n-flex :size="0" align="center" class="mx-auto" justify="center">
			<n-image :img-props="{ class: 'w-50' }" :src="avatar"/>

			<n-flex class="<sm:text-center" vertical>
				<n-flex :size="0" class="leading-none" vertical>
					<n-text class="text-5xl fw-extrabold">Abnormal Cat</n-text>
					<n-text class="text-2xl text-pink-200 fw-bold">猫老师</n-text>
				</n-flex>

				<n-text :depth="3" class="text-xl">一位业余的建模师和小小的 Unity / VRChat 创作者</n-text>
			</n-flex>
		</n-flex>

		<n-flex :align="isMobile ? 'center' : undefined" :vertical="isMobile" justify="center">
			<n-button :block="isMobile" href="https://qm.qq.com/q/BRkMmYgP5Y" tag="a">
				<template #icon>
					<n-icon :component="QqOutlined"/>
				</template>

				QQ
			</n-button>

			<n-button :block="isMobile" href="mailto:3318415065@qq.com" tag="a">
				<template #icon>
					<n-icon :component="MailOutlined"/>
				</template>

				邮箱
			</n-button>

			<n-button :block="isMobile" href="https://vrchat.com/home/user/usr_245af4df-3061-4aef-86bc-0cd27668b8eb"
					  tag="a">
				<template #icon>
					<Icons-Vr/>
				</template>

				VRChat
			</n-button>

			<n-button
				:block="isMobile"
				href="https://qm.qq.com/cgi-bin/qm/qr?k=7qfcxHxFgp9ToI19wepmGTGIzSYwVr68&authKey=PeN0iwzyLwMjQ0idbOCcSD4EQkDbxxAYc3vOCmawQr53sVTgqd4JDsd2lcdaRj0K"
				tag="a">
				<template #icon>
					<n-icon :component="UsergroupAddOutlined"/>
				</template>

				粉丝群
			</n-button>
		</n-flex>

		<template v-if="isMobile">
			<n-divider class="!my-2"/>
		</template>

		<n-flex :align="isMobile ? 'center' : undefined" :vertical="isMobile" justify="center">
			<n-button :block="isMobile" href="https://space.bilibili.com/454104032" tag="a">
				<template #icon>
					<Icons-BiliBili/>
				</template>

				哔哩哔哩
			</n-button>

			<n-button :block="isMobile" :href="supportPageLink.href.value" tag="a"
					  @click.prevent="supportPageLink.navigate()">
				<template #icon>
					<n-icon :component="HeartOutlined"/>
				</template>

				支持 & 赞助
			</n-button>

			<n-button :block="isMobile" href="https://m.tb.cn/h.TIwLCkP?tk=tzeueR7pjH1" tag="a">
				<template #icon>
					<Icons-Fish/>
				</template>

				闲鱼
			</n-button>
		</n-flex>

		<n-divider>视频 & 作品</n-divider>

		<n-flex vertical>
			<iframe class="border-none w-full aspect-video"
					src="https://player.bilibili.com/player.html?aid=116273455302875&autoplay=0"/>

			<n-flex :vertical="isMobile" justify="space-evenly">
				<n-element class="flex-1">
					<iframe class="border-none aspect-video"
							src="https://player.bilibili.com/player.html?aid=114208834323611&autoplay=0"/>
				</n-element>

				<n-element class="flex-1">
					<iframe class="border-none aspect-video"
							src="https://player.bilibili.com/player.html?aid=115879626934213&autoplay=0"/>
				</n-element>
			</n-flex>
		</n-flex>

		<n-divider class="!my-4">文件</n-divider>

		<n-list bordered>
			<n-list-item v-for="downloadableAsset in downloadableAssets">
				<n-button
					:download="decodeURIComponent(downloadableAsset.split('/').at(-1) ?? '?')"
					:href="downloadableAsset"
					tag="a"
					text
					type="primary"
				>
					{{ decodeURIComponent(downloadableAsset.split('/').at(-1) ?? '?') }}
				</n-button>
			</n-list-item>
		</n-list>
	</n-flex>
</template>
