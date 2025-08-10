<script lang="ts">
  import { onMount, createEventDispatcher } from "svelte";
  import { page } from "../stores/page";

  const dispatch = createEventDispatcher();

  let buttonContainer: HTMLElement;

  onMount(() => {
    setTimeout(() => {
      if (buttonContainer) {
        buttonContainer.style.bottom = "0px";
      }
    }, 500);
  });

  function navigateTo(pageNumber: number) {
    dispatch("navigate", pageNumber);
  }
</script>

<div bind:this={buttonContainer} id="ButtonContainer">
  <button on:click={() => navigateTo(0)} class:selected={$page === 0}> Home Page </button>
  <button on:click={() => navigateTo(1)} class:selected={$page === 1}> Social media </button>
  <button on:click={() => navigateTo(2)} class:selected={$page === 2}> Work Projects </button>
  <button on:click={() => navigateTo(3)} class:selected={$page === 3}>
    Songs<br />(Original / Remix)
  </button>
</div>

<style>
	#ButtonContainer {
		bottom: -8%;
		width: 100%;
		height: 8%;
		position: fixed;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		transition: bottom 2s;
	}

	button {
		background: black;
		opacity: 0.4;
		border: none;
		color: white;
		cursor: pointer;
		flex-grow: 1;
		font-size: 1.5rem;
		transition:
			opacity 0.3s,
						background-color 0.3s;
	}

	button.selected {
		opacity: 1;
		background: unset;
	}

	button:hover {
		opacity: 0.8;
	}

	@media (max-width: 768px) {
		button {
			font-size: 1rem;
		}
	}
</style>
