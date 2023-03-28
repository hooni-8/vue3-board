<template>
	<div>
		<h2>About View</h2>
		<p>{{ $route.path }}</p>
		<p>{{ $route.name }}</p>
		<button class="btn btn-primary" @click="$router.push('/')">
			Home으로 이동
		</button>
		<hr class="my-4" />
		<h2>Store</h2>
		<p>counter: {{ counter }}</p>
		<p>doubleCounter: {{ doubleCount }}</p>
		<p>doubleCountPlusOne: {{ doubleCountPlusOne }}</p>
		<button @click="increment()">Click!</button>
	</div>
</template>

<script setup>
import { useRoute } from 'vue-router';
import { useCounterStore } from '@/stores/counter';
import { storeToRefs } from 'pinia';
const route = useRoute();
console.log('route.path: ', route.path);

const store = useCounterStore();

const { counter, doubleCount, doubleCountPlusOne } = storeToRefs(store);
const { increment } = store;
counter.value = 1000;
</script>

<style lang="scss" scoped></style>
