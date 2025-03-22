<script lang="ts" setup>
import '~/scripts/sakura'

import { HeartOutlined, MailOutlined, QqOutlined, UsergroupAddOutlined } from '@vicons/antd'
import avatar from '~/assets/avatar.png'

import doc_1 from '~/assets/download/1.docx?url'
import doc_2 from '~/assets/download/2.docx?url'
import doc_3 from '~/assets/download/3.docx?url'
import doc_4 from '~/assets/download/4.docx?url'

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
				<n-text class="text-5xl fw-bold">Abnormal Cat</n-text>
				<n-text :depth="3" class="text-xl">一位业余的建模师和小小的 Unity / VRChat 创作者</n-text>
			</n-flex>
		</n-flex>

		<n-flex justify="center">
			<n-button href="https://wpa.qq.com/msgrd?uin=3318415065" tag="a">
				<template #icon>
					<n-icon :component="QqOutlined"/>
				</template>

				QQ
			</n-button>

			<n-button href="mailto:3318415065@qq.com" tag="a">
				<template #icon>
					<n-icon :component="MailOutlined"/>
				</template>

				邮箱
			</n-button>

			<n-button href="https://vrchat.com/home/user/usr_245af4df-3061-4aef-86bc-0cd27668b8eb" tag="a">
				<template #icon>
					<Icons-Vr/>
				</template>

				VRChat
			</n-button>

			<n-button
				href="https://qm.qq.com/cgi-bin/qm/qr?k=7qfcxHxFgp9ToI19wepmGTGIzSYwVr68&authKey=PeN0iwzyLwMjQ0idbOCcSD4EQkDbxxAYc3vOCmawQr53sVTgqd4JDsd2lcdaRj0K"
				tag="a">
				<template #icon>
					<n-icon :component="UsergroupAddOutlined"/>
				</template>

				粉丝群
			</n-button>
		</n-flex>

		<n-flex justify="center">
			<n-button href="https://space.bilibili.com/454104032" tag="a">
				<template #icon>
					<Icons-BiliBili/>
				</template>

				哔哩哔哩
			</n-button>

			<n-button :href="supportPageLink.href.value" tag="a" @click.prevent="supportPageLink.navigate()">
				<template #icon>
					<n-icon :component="HeartOutlined"/>
				</template>

				支持 & 赞助
			</n-button>

			<n-button href="https://m.tb.cn/h.TIwLCkP?tk=tzeueR7pjH1" tag="a">
				<template #icon>
					<Icons-Fish/>
				</template>

				闲鱼
			</n-button>
		</n-flex>

		<n-divider>视频 & 作品</n-divider>

		<n-grid :x-gap="10" :y-gap="10" cols="1 s:3" responsive="screen">
			<n-grid-item>
				<iframe class="border-none w-full h-[25vh]"
						src="https://player.bilibili.com/player.html?aid=1400265936&autoplay=0"/>
			</n-grid-item>

			<n-grid-item>
				<iframe class="border-none w-full h-[25vh]"
						src="https://player.bilibili.com/player.html?aid=114008044604317&autoplay=0"/>
			</n-grid-item>

			<n-grid-item>
				<iframe class="border-none w-full h-[25vh]"
						src="https://player.bilibili.com/player.html?aid=114001820257300&autoplay=0"/>
			</n-grid-item>

			<n-grid-item :span="3">
				<n-flex :size="10" :wrap="false" justify="space-evenly">
					<iframe class="border-none w-full h-[25vh]"
							src="https://player.bilibili.com/player.html?aid=687077176&autoplay=0"/>

					<iframe class="border-none w-full h-[25vh]"
							src="https://player.bilibili.com/player.html?aid=389441034&autoplay=0"/>
				</n-flex>
			</n-grid-item>
		</n-grid>

		<n-divider>文档</n-divider>

		<n-list bordered>
			<n-list-item>
				<n-button :href="doc_1" download="艾斯杀手娘玩法介绍.docx" tag="a" text type="primary">
					艾斯杀手娘玩法介绍.docx
				</n-button>
			</n-list-item>

			<n-list-item>
				<n-button :href="doc_2" download="新杰顿娘玩法介绍.docx" tag="a" text type="primary">
					新杰顿娘玩法介绍.docx
				</n-button>
			</n-list-item>

			<n-list-item>
				<n-button :href="doc_3" download="新佐菲玩法介绍.docx" tag="a" text type="primary">新佐菲玩法介绍.docx
				</n-button>
			</n-list-item>

			<n-list-item>
				<n-button :href="doc_4" download="哥莫拉模型玩法介绍.docx" tag="a" text type="primary">
					哥莫拉模型玩法介绍.docx
				</n-button>
			</n-list-item>
		</n-list>
	</n-flex>
</template>