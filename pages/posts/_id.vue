<template>
	<div class="container">
		<article>
			<h1 class="title">
				{{ (post !== undefined)? post.title : latest.title }}
			</h1>
			<p>
				{{ (post !== undefined)? post.body : latest.title }}
			</p>
		</article>
		<aside>
			<h3>Posts you might also enjoy</h3>
			<ul>
				<li v-for="related in relatedPosts" :key="related.id">
					<nuxt-link :to="{ name: 'posts-id', params: {id: related.id}}">{{ related.title }}</nuxt-link>
				</li>
			</ul>
		</aside>
	</div>
</template>

<script>
export default {
	data() {
		return {
			id: this.$route.params.id
		}
	},
	head() {
		return {
			title: `${this.post.title} 📃`,
			meta: [
				{
					name: 'twitter:title',
					content: this.post.title
				},
				{
					name: 'twitter:description',
					content: this.post.content
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
		}
	},
	computed: {
		post() {
			return (this.id) ? this.$store.state.posts.all.find(p => p.id === this.id) : this.latest
		},
		relatedPosts() {
			return this.$store.state.posts.all.filter(p => (this.id) ? (p.id !== this.id) : (p.id !== this.latest.id))
		},
		latest() {
			return this.$store.state.posts.all[this.$store.state.posts.all.length - 1]
		}
	}
};
</script>

<style scoped>
.container {
	display: flex;
	justify-content: space-between;
	line-height: 1.5;
}
article * {
	margin-bottom: 1rem;
}
aside {
	min-width: 280px;
	max-width: 280px;
	padding-left: 2rem;
}
.title {
	font-size: 2rem;
}
</style>