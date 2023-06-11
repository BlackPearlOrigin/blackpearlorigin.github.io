<script lang="ts">
	import {
		Navbar,
		NavBrand,
		NavHamburger,
		DarkMode,
		Gallery,
		GradientButton,
	} from 'flowbite-svelte';

	import { LogoApple, LogoTux, LogoWindows } from 'svelte-ionicons';

	type OS = 'Linux' | 'Windows' | 'Mac';

	const downBtn = (os: OS) => {
		switch (os) {
			case 'Linux':
				window.open('', '_newpage');
				break;
			case 'Windows':
				window.open('', '_newpage');
				break;
			case 'Mac':
				window.open('', '_newpage');
				break;
		}
	};

	const image = [{ alt: 'An image of BPO', src: 'App-res.png' }];
</script>

<main class="relative px-8">
	<Navbar
		navClass="navbar px-2 sm:px-4 py-2.5 absolute w-full z-20 top-0 left-0 border-b"
		let:hidden
		let:toggle
	>
		<NavBrand href="/">
			<img
				src="logo.svg"
				class="dark:invert mr-3 h-6 sm:h-9"
				alt="Flowbite Logo"
			/>
		</NavBrand>
		<NavHamburger on:click="{toggle}" />
		<DarkMode />
	</Navbar>
	<div class="gradient-bg">
		<div class="main-content">
			<p class="text-6xl font-black text-center text-white">
				<span class="underline decoration-sky-300">Simple</span> and
				<span class="underline decoration-sky-300">Effortless</span> Library
				Management
			</p>
			<p class="pt-3 text-xl font-medium text-center text-white">
				Black Pearl Origin (BPO) is a FOSS library management app with a
				built in search feature, plugin system and intuitive UI.
			</p>

			<div class="flex justify-center pt-[4rem]">
				<div class="shadow-2xl ml-3 mr-3">
					<GradientButton
						on:click="{() => downBtn('Windows')}"
						color="cyanToBlue"
					>
						<LogoWindows class="mt-1 mb-1" size="48px" />
					</GradientButton>
				</div>
				<div class="shadow-2xl ml-3 mr-3">
					<GradientButton
						on:click="{() => downBtn('Mac')}"
						color="cyanToBlue"
					>
						<LogoApple class="mt-1 mb-1" size="48px" />
					</GradientButton>
				</div>
				<div class="shadow-2xl ml-3 mr-3">
					<GradientButton
						on:click="{() => downBtn('Linux')}"
						color="cyanToBlue"
					>
						<LogoTux class="mt-1 mb-1" size="48px" />
					</GradientButton>
				</div>
			</div>

			<Gallery class="flex justify-center mt-[4rem]" items="{image}" />
		</div>
	</div>
</main>
