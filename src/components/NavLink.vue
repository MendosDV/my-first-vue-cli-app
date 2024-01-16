<script>
export default {
	name: 'NavLink',
  props: ['url', 'text']
}
</script>

<template>
	<a v-bind:href="url">{{ text }}</a>
</template>

<style>
	a {
		text-decoration: none;
	}
</style>
