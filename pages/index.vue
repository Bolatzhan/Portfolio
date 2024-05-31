<script setup>
	const { data: posts } = await useAsyncData("latest-posts", () =>
		queryContent("/blog").sort({ data: 1 }).limit(3).find()
	);
</script>

<template>
	<section>
		<h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Bolatzhan!</h1>
		<p class="text-base text-gray-900 p-2 italic">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores, in!
		</p>
	</section>
	<section class="flex flex-col md:flex-row">
		<div class="md:w-3/4">
			<h2 class="text-3xl font-bold mt-8">My Story</h2>
			<p class="text-lg py-2">
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt velit
				numquam fugiat, aperiam impedit quas labore, sint laudantium voluptatem
				dolor praesentium consequatur omnis soluta placeat animi sapiente quos
				laborum eos.
			</p>
			<p class="text-lg py-2">
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Architecto
				esse alias dolor ad, dolorem quas dolorum! Facere eveniet dolorem
				voluptatibus?
			</p>
			<p class="text-lg py-2">
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatem,
				possimus doloremque similique beatae quia obcaecati libero dicta. Facere
				reprehenderit, saepe voluptate assumenda suscipit dignissimos id?
				Possimus laborum nulla sequi sapiente?
			</p>
		</div>
		<!-- <img
			src="~/assets/images/danvega-avatar.png"
			class="w-1/2 md:max-w-sm p-8 mx-auto"
		/> -->
	</section>

	<section>
		<h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
		<div class="grid md:grid-cols-3 pt-8 gap-10">
			<Post :posts="posts" />
		</div>
	</section>
</template>

<style scoped></style>
