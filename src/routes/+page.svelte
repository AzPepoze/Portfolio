<script lang="ts">
	import { onMount } from "svelte";
	import BackgroundImage from "$lib/components/BackgroundImage.svelte";
	import BottomNav from "$lib/components/BottomNav.svelte";
	import HomePage from "$lib/components/pages/HomePage.svelte";
	import LoadScreen from "$lib/components/LoadScreen.svelte";
	import MouseEffects from "$lib/components/MouseEffects.svelte";
	import ProjectsPage from "$lib/components/pages/ProjectsPage.svelte";
	import SongsPage from "$lib/components/pages/SongsPage.svelte";
	import SocialsPage from "$lib/components/pages/SocialsPage.svelte";
	import { page } from "$lib/stores/page";

	let scrollLeft = 0;
	let mainContainer: HTMLElement;

	function handleScroll() {
		if (mainContainer) {
			scrollLeft = mainContainer.scrollLeft;
			const currentPage = Math.round(scrollLeft / window.innerWidth);
			page.set(currentPage);
		}
	}

  const handleWheel = (e: WheelEvent) => {
    if (e.deltaY === 0 || !mainContainer) return;

    mainContainer.scrollTo({
      left: mainContainer.scrollLeft + (e.deltaY > 0 ? window.innerWidth : -window.innerWidth),
      behavior: "smooth",
    });
    e.preventDefault();
  };

  function handleNavigate(event: CustomEvent<number>) {
    const pageNumber = event.detail;
    if (!mainContainer) return;

    mainContainer.scrollTo({
      top: 0,
      left: pageNumber * window.innerWidth,
      behavior: "smooth",
    });
  }

	onMount(() => {
		if (mainContainer) {
			mainContainer.addEventListener("scroll", handleScroll);
      mainContainer.addEventListener("wheel", handleWheel, { passive: false });
		}

		return () => {
			if (mainContainer) {
				mainContainer.removeEventListener("scroll", handleScroll);
        mainContainer.removeEventListener("wheel", handleWheel);
			}
		};
	});
</script>

<main bind:this={mainContainer}>
	<BackgroundImage {scrollLeft} />
	<LoadScreen />
	<MouseEffects />

	<div class="pages">
		<section id="page-0">
			<HomePage />
		</section>
		<section id="page-1">
			<SocialsPage />
		</section>
		<section id="page-2">
			<ProjectsPage />
		</section>
		<section id="page-3">
			<SongsPage />
		</section>
	</div>

	<BottomNav on:navigate={handleNavigate} />
</main>

<style>
	main {
		width: 100vw;
		height: 100%;
		overflow-x: scroll;
		overflow-y: hidden;
		scroll-snap-type: x mandatory;
		scroll-behavior: smooth;
	}

	.pages {
		display: flex;
		width: 400vw; /* 4 pages */
		height: 100%;
	}

	section {
		width: 100vw;
		height: 100%;
		scroll-snap-align: start;
		scroll-snap-stop: always;
	}
</style>