<template>
	<a :href="href" target="_blank">
		<slot></slot>
	</a>
</template>

<script>
export default {
	props: ['href'],

}
</script>

<style lang="scss" scoped>
a {
	display: inline-block;
    font-size: 1.1rem;
    color: rgb(27, 27, 27);
    padding: 8px 15px;
    border: 1px solid #4f4f4f;
    background-color: #f3f3f3;
	margin-right: 25px;
	transition: .3s all;

	&:hover {
		background-color: #4f4f4f;
		color: #Fff;
	}
}
</style>