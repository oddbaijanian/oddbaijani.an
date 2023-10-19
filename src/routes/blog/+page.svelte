<script lang="ts">
	export let data;
	console.log(data.posts)
</script>

<div
	class="flex justify-between px-8 text-text min-w-screen h-10 items-center bg-bgsecondary shadow-xl"
>
	<a href="/" class="font-bold">odd</a>
	<div class=" flex gap-10">
		<a href="/about" class="font-normal">About</a>
		<a href="/blog" class="font-normal">Blog</a>
	</div>
</div>

<div class="flex flex-col w-full gap-y-4 min-h-screen px-32">
	<div class="flex justify-center text-2xl mt-12 px-4 text-text">
		<span class="font-bold text-2xl text-center"> Latest Posts </span>
	</div>
	<div class="flex flex-col  items-center w-full gap-y-4 justify-center px-72 text-text">
		{#each data.posts as post }
			<div class="flex flex-col w-[340px] min-w-[240px] bg-bgsecondary">
				<img class="rounded-t-sm min-w-[240px] h-[125px]" src="https://cdn.discordapp.com/attachments/1144428111040106608/1164143495221624832/wallhaven-d6o77l.jpg?ex=6542241e&is=652faf1e&hm=f1e5fce4398eeedbe5fa83edeb4ad1e0bca55e1e70d07103590be3a86085c905&" alt="">
				<div class="px-4 py-2">
					<div class="flex flex-row gap-x-2 mt-2">
						{#each post.hashtag as  hashtag}
							<span class="text-center border-[0.5px] p-[4px] text-xs bg-bgsecondary border-[#222222]">
								<a href="/" class="hover:underline hover:cursor-pointer">
									#{hashtag}
								</a>
							</span>
						{/each}
						</div>
						<p class="text-md font-semibold mt-2">{post.title}</p>
						<p class="text-xs text-[#a8a8a8] mt-2 mb-2 font-normal">{post.description}</p>
					<div class="flex flex-row justify-between mt-10 mb-2 items-center">
						<div class="flex flex-row items-center">
							<img src="https://api.lanyard.rest/1149375668057034752.png" class="rounded-full w-4 h-4" alt=""> <p class="text-xs text-center ml-[0.20rem]">{post.author}</p>
						</div>
						<div>
							<p class="text-xs text-center">{post.date.toLocaleString()}</p>
						</div>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>
