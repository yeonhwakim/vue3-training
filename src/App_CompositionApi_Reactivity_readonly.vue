<template>
	<div></div>
</template>

<script>
import { reactive, readonly } from 'vue'
export default {
	setup() {
		const original = reactive({ count: 0 })

		const copy = readonly(original)

		// 원본이 변이되면 복사본에 의존하는 watch 도 트리거
		original.count++

		// 복사본을 변이하려고 하면 경고와 함께 실패
		copy.count++ // warning
		return {}
	},
}
</script>

<style lang="scss" scoped></style>
