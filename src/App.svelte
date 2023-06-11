<script lang="ts">
	import {
		Navbar,
		NavBrand,
		NavHamburger,
		DarkMode,
		Gallery,
		GradientButton,
		Button,
	} from 'flowbite-svelte';

	import {
		LogoApple,
		LogoTux,
		LogoWindows,
		LogoDiscord,
		LogoGithub,
	} from 'svelte-ionicons';

	type OS = 'Linux' | 'Windows' | 'Mac';
	type Social = 'Discord' | 'Github';

	const downBtn = (os: OS) => {
		switch (os) {
			case 'Linux':
				window.open(
					'https://github.com/BlackPearlOrigin/blackpearlorigin/releases/latest/',
					'_newpage'
				);
				break;
			case 'Windows':
				window.open(
					'https://github.com/BlackPearlOrigin/blackpearlorigin/releases/latest/',
					'_newpage'
				);
				break;
			case 'Mac':
				window.open(
					'https://github.com/BlackPearlOrigin/blackpearlorigin/releases/latest/',
					'_newpage'
				);
				break;
		}
	};

	const socialLinks = (social: Social) => {
		if (social === 'Discord') {
			window.open('https://discord.gg/WpBr3hJVf5', '_newpage');
		} else {
			window.open('https://github.com/BlackPearlOrigin', '_newpage');
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

		<div class="flex row-auto">
			<Button
				on:click="{() => socialLinks('Discord')}"
				btnClass="text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 
				focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg 
				text-sm p-2.5 mr-2"
			>
				<LogoDiscord
					class="dark:fill-[#9ca3af] pl-0 pr-0 fill-[#6b7280]"
				/>
			</Button>
			<Button
				on:click="{() => socialLinks('Github')}"
				btnClass="text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 
				focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg 
				text-sm p-2.5 mr-2"
			>
				<LogoGithub
					class="dark:fill-[#9ca3af] pl-0 pr-0 fill-[#6b7280]"
				/>
			</Button>
			<DarkMode />
		</div>
	</Navbar>
	<div class="gradient-bg">
		<div class="main-content">
			<p class="text-6xl font-black text-center text-white pl-5 pr-5">
				<span class="underline decoration-sky-300">Simple</span> and
				<span class="underline decoration-sky-300">Effortless</span> Library
				Management
			</p>
			<p
				class="pt-3 text-xl font-medium text-center text-white pl-5 pr-5"
			>
				Black Pearl Origin (BPO) is a FOSS game library management app
				with a built in search feature, plugin system and intuitive UI.
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

			<Gallery
				class="flex justify-center mt-[4rem] pl-5 pr-5"
				items="{image}"
			/>
		</div>
	</div>
</main>
