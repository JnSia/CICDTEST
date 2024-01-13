<template>
  <div v-if="props.streamManager">
    <OvVideo :stream-manager="props.streamManager" />
    <div>
      <p style="color: wheat;">{{ clientData }}</p>
    </div>
  </div>
</template>

<script setup>
import { computed, defineProps } from 'vue';
import OvVideo from './OvVideo.vue';

const props = defineProps({
	streamManager: Object
})

const clientData = computed(() => {
	const { clientData } = getConnectionData();
	return clientData;
})

const getConnectionData = () => {
	const { connection } = props.streamManager.stream;
	return JSON.parse(connection.data);
}
</script>
