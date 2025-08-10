<script>
	import Page from "../Page.svelte";
</script>

<Page>
	<div class="LeftFrame">
		<div class="SubText CenterText Large bold">🌐 My social media 🌐</div>
	</div>

	<div class="RightFrame">
		<a
			href="https://www.youtube.com/channel/UCJ2C0UTfxQo6iGTfudPfoRQ"
			target="_blank"
			class="socialbutton box-shadow-red"
		>
			<img
				class="rounded-full mr-2"
				src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/YouTube_full-color_icon_%282017%29.svg/2560px-YouTube_full-color_icon_%282017%29.svg.png"
				alt="Youtube"
			/>
			Yoututbe : AzPepoze
		</a>

		<a href="https://www.pixiv.net/en/users/44970537" target="_blank" class="socialbutton box-shadow-blue">
			<img
				class="rounded-full mr-2"
				src="https://is5-ssl.mzstatic.com/image/thumb/Purple116/v4/65/cc/d2/65ccd259-6ed6-4e34-20f0-d83018f6663a/AppIcon-0-1x_U007emarketing-0-7-0-85-220.png/512x512bb.jpg"
				alt="Pixiv"
			/>
			Pixiv : AzPepoze
		</a>

		<a href="https://www.tiktok.com/@azpepoze_1" target="_blank" class="socialbutton box-shadow-purple">
			<img
				class="rounded-full mr-2"
				src="https://img.freepik.com/premium-vector/tik-tok-logo_578229-290.jpg"
				alt="Tiktok"
			/>
			Tiktok : azpepoze_1
		</a>
	</div>
</Page>

<style>
	.socialbutton {
		transition: all 0.3s ease;
		margin: 10px; /* Adjusted margin */
		background-color: rgba(0, 0, 0, 0.6); /* Adjusted background */
		display: flex;
		align-content: center;
		justify-content: flex-start;
		align-items: center;
		padding: 10px 20px; /* Adjusted padding */
		text-decoration: none;
		width: 50%;
		min-width: 250px; /* Fixed width */
		font-size: 130%; /* Adjusted font size */
		border: 1px solid transparent;
		border-radius: 9999px;
	}

	.socialbutton:hover {
		background-color: rgba(255, 255, 255, 0.9);
		color: black;
		font-weight: 900;
		box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.5);
		transform: scale(1.1);
		border-color: white;
	}

	.socialbutton img {
		height: 15%;
		width: 15%;
		aspect-ratio: 1;
		object-fit: cover;
		border-radius: 9999px;
		transition: all 0.5s;
		margin-right: 10px;
	}

	/* Original box-shadow classes */
	.box-shadow-red {
		box-shadow: red 0px 0px 6px;
	}

	.box-shadow-blue {
		box-shadow: rgb(0, 132, 255) 0px 0px 6px;
	}

	.box-shadow-purple {
		box-shadow: rgb(186, 84, 255) 0px 0px 6px;
	}
</style>
