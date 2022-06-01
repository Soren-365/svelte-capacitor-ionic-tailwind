<script>
	const greet = () => alert('hello MisaTv!');
</script>

<ion-app>
	<ion-content>
		<ion-header>
			<ion-toolbar>
				<ion-title>My-APP</ion-title>
			</ion-toolbar>
		</ion-header>
		<slot />

		<ion-footer>
			<ion-button color="secondary" expand="block" on:click={greet}> Greet </ion-button>
		</ion-footer>
	</ion-content>
</ion-app>
