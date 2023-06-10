<script>
	import { Alert, DarkMode, Gallery, Skeleton } from 'flowbite-svelte';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte'
	import { GradientButton } from 'flowbite-svelte';

	const downBtn = () => {
		window.open("https://github.com/BlackPearlOrigin/blackpearlorigin", "_newpage")
	}

	const image = [
		{ alt: "An image of BPO", src: "App.png"}
	]
</script>

<main class="relative px-8">
	<Navbar 
		navClass="navbar px-2 sm:px-4 py-2.5 absolute w-full z-20 top-0 left-0 border-b"
		let:hidden 
		let:toggle>
		<NavBrand href="/">
		  <img
			src="logo.svg"
			class="dark:invert mr-3 h-6 sm:h-9"
			alt="Flowbite Logo"
		  />
		</NavBrand>
		<NavHamburger on:click={toggle} />
		<NavUl {hidden}>
		  <NavLi href="/" active={true}>Home</NavLi>
		  <NavLi href="/about">About</NavLi>
		  <NavLi href="/services">Services</NavLi>
		  <NavLi href="/pricing">Pricing</NavLi>
		  <NavLi href="/contact">Contact</NavLi>
		</NavUl>

		<DarkMode></DarkMode>
	  </Navbar>

	<div class="main-content">
		<p class="text-6xl font-black text-center text-white">
			<span class="underline decoration-sky-300">Simple</span> and <span class="underline decoration-sky-300">Effortless</span> Library Management
		</p>
		<p class="pt-3 text-xl font-medium text-center text-white">Black Pearl Origin (BPO) is a FOSS library management app with a built in search feature, plugin system and intuitive UI.</p>
		
		<div class="flex justify-center pt-7">
			<div class="shadow-2xl">
				<GradientButton on:click={downBtn} color="cyanToBlue" ><span class="text-xl text-white">Install BPO</span></GradientButton>
			</div>
		</div>

		<Gallery class="flex justify-center scale-75" items={image}></Gallery>
	</div>
</main>