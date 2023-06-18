<script lang="ts">
	import {
		Navbar,
		NavBrand,
		DarkMode,
		Gallery,
		GradientButton,
		Button,
		Card,
	} from 'flowbite-svelte';

	import {
		LogoApple,
		LogoTux,
		LogoWindows,
		LogoDiscord,
		LogoGithub,
		LockOpenOutline,
		ExtensionPuzzleOutline,
		SparklesOutline,
		AccessibilityOutline,
	} from 'svelte-ionicons';

	import {
		Footer,
		FooterCopyright,
		FooterLinkGroup,
		FooterLink,
	} from 'flowbite-svelte';

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
				src="logoLight.svg"
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
			<DarkMode initialTheme="dark" class="invisible" />
		</div>
	</Navbar>
	<div class="gradient-bg">
		<div class="title-section">
			<p class="text-6xl font-black text-center text-white pl-5 pr-5">
				<span class="underline decoration-sky-300">Simple</span> and
				<span class="underline decoration-sky-300">Effortless</span> Library
				Management
			</p>
			<p
				class="pt-3 text-2xl font-medium text-center text-white pl-5 pr-5"
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
				class="flex justify-center mt-[4rem] pl-5 pr-5 pb-[11rem]"
				items="{image}"
			/>
		</div>

		<div class="secondary-section">
			<p class="text-6xl font-black text-center text-white pl-5 pr-5">
				Cross-Platform Game Library.
			</p>

			<p
				class="text-6xl font-black text-center text-white pl-5 pr-5 pt-2"
			>
				Powered by the
				<span class="underline decoration-sky-300"> Web </span>
			</p>

			<p
				class="pt-6 text-2xl font-medium text-center text-white pl-10 pr-10"
			>
				Black Pearl Origin (BPO) utilizes the <a
					class="text-sky-500"
					href="https://tauri.app">Tauri Framework</a
				>
				for cross-compatibility, is written with
				<a class="text-sky-500" href="https://svelte.dev">Svelte</a>
				for a clean frontend, and built with
				<a class="text-sky-500" href="https://rust-lang.org">Rust</a> for
				the backend to provide a blazingly fast experience
			</p>
		</div>

		<div class="flex flex-row justify-around mb-[8rem]">
			<Card class="dark:bg-slate-800 ">
				<span class="flex flex-row font-bold text-white text-3xl pb-3">
					<LockOpenOutline size="32" />

					<span class="pl-2"> Open Source </span>
				</span>
				<p class="font-normal text-white text-xl">
					Black Pearl Origin (BPO) is an innovative app that embraces
					the spirit of collaboration and transparency by being fully
					open source. This means that developers and enthusiasts can
					explore, modify, and contribute to its codebase, ensuring a
					constantly evolving and community-driven experience.
				</p>
			</Card>

			<Card class="dark:bg-slate-800">
				<span class="flex flex-row font-bold text-white text-3xl pb-3">
					<ExtensionPuzzleOutline size="33" class="dark:invert" />

					<span class="pl-2"> Plugin System </span>
				</span>
				<p class="font-normal text-white text-xl">
					With BPO's powerful plugin system, finding games has never
					been easier. Our app offers an extensive library of plugins
					that allow you to search and discover your favorite games
					with just a few clicks. Whether you're a casual gamer or a
					hardcore enthusiast, our plugin system ensures you'll always
					have access to the latest and most relevant gaming content.
				</p>
			</Card>

			<Card class="dark:bg-slate-800">
				<span class="flex flex-row font-bold text-white text-3xl pb-3">
					<SparklesOutline size="33" class="dark:invert" />

					<span class="pl-2"> Clean and Intuitive UI</span>
				</span>
				<p class="font-normal text-white text-xl">
					BPO boasts a clean and intuitive user interface that makes
					navigating the app a breeze. The carefully crafted design
					prioritizes simplicity and elegance, ensuring that users can
					effortlessly browse through various games without feeling
					overwhelmed. Say goodbye to cluttered interfaces and hello
					to a visually pleasing experience with BPO.
				</p>
			</Card>

			<Card class="dark:bg-slate-800">
				<span class="flex flex-row font-bold text-white text-3xl pb-3">
					<AccessibilityOutline size="33" class="dark:invert" />

					<span class="pl-2"> Easy to Use</span>
				</span>
				<p class="font-normal text-white text-xl">
					BPO takes pride in its user-friendly nature, making it
					accessible to users of all skill levels. From downloading to
					daily usage, our app streamlines the process, minimizing any
					learning curve. With clear instructions and intuitive
					features, you can quickly and easily find the games you're
					looking for, making your gaming experience more enjoyable
					from start to finish.
				</p>
			</Card>
		</div>
		<Footer class="dark:bg-slate-900">
			<FooterCopyright
				href="/"
				by="Black Pearl Origin's Contributors"
				year="{2023}"
			/>
			<FooterLinkGroup
				ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0"
			>
				<FooterLink href="https://discord.com/WpBr3hJVf5"
					>Discord</FooterLink
				>
				<FooterLink href="https://github.com/BlackPearlOrigin"
					>Github</FooterLink
				>
				<FooterLink href="mailto:blackpearlorigin@proton.me"
					>Contact</FooterLink
				>
			</FooterLinkGroup>
		</Footer>
	</div>
</main>
