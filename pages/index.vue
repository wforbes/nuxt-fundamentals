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
				href="/about"
				class="button--green"
			>
				About
			</a>
			<a
				href="/posts"
				class="button--green"
			>
				Posts
			</a>
		</div>
		<div class="posts">
			<span class="post" v-for="post in posts" :key="post.id">
				<nuxt-link :to="{ name:'posts-id', params: { id: post.id }}" class="button--grey">{{ post.title }}</nuxt-link>
			</span>
		</div>
  	</section>
</template>

<script>
export default {
	head: {
		title: "Home Page 🤓",
		meta: [
				{
					name: 'twitter:title',
					content: 'Nuxt Fundamentals site'
				},
				{
					name: 'twitter:description',
					content: 'A simple website made with Nuxt to learn the fundamentals'
				},
				{
					name: 'twitter:image',
					content: 'https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2070&q=80'
				},
				{
					name: 'twitter:card',
					content: 'summary-large-image'
				}
			]
	},
	computed: {
		posts() {
			return this.$store.state.posts.all;
		}
	}
}
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
.posts {
	padding-top: 1em;
}
</style>
