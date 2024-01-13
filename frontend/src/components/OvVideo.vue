<template>
	<video ref="video" autoplay></video>
</template>

<script setup>
import { ref, defineProps, onMounted } from 'vue';

const video = ref(null)

const props = defineProps({
	streamManager: Object
})

onMounted(() => {
	if (props.streamManager){
		props.streamManager.addVideoElement(video.value)	
	}
})
</script>
