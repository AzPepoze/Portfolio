<script lang="ts">
	export let scrollLeft = 0;
</script>

<img
	id="BG"
	style:filter={`hue-rotate(${scrollLeft / 20}deg)`}
	src="https://i.imgur.com/Nglfni6.png"
	alt="Background"
/>

<style>
	#BG {
		position: fixed;
		z-index: -1;
		top: 0;
		width: 100%;
		height: 100%;
		opacity: 0.3;
		object-fit: cover;
	}
</style>
