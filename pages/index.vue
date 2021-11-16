<template>
	<section class="container">
		<div class="jumbo">
	    	<WfLogo />
		</div>
		<h1 class="title">
			will forbes
		</h1>
		<h2 class="sub-title">
			nuxt-fundamentals site
		</h2>
		<div class="links">
			<a
				href="#"
				class="button--grey"
			>
				About
			</a>
			<a
				href="#"
				class="button--green"
			>
				Documentation
			</a>
		</div>
  	</section>
</template>

<script>
export default {}
</script>

<style scoped>
.container {
	font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
		'Segoe UI', Roboto;
	min-height: 100vh;
	text-align: center;
}
.jumbo {
	margin-top: 3em;
	display:block;
}
.title {
	color: #7e61f3;
	display: block;
	font-weight: 700;
	font-size: 75px;
	letter-spacing: 1px;
	margin: 0;
	padding: 0;
}
.sub-title {
	color: #26add4;
	margin-top: 0;
	display: block;
}
.links {
	display: block;
	padding-top: 1em;
}
</style>
