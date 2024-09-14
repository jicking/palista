<script lang="ts">
	import TopAppBar, { Row, Section, Title, AutoAdjust } from '@smui/top-app-bar';
	import IconButton from '@smui/icon-button';

	let topAppBar: TopAppBar;
</script>

<TopAppBar bind:this={topAppBar} variant="fixed" dense>
	<Row>
		<Section>
			<IconButton class="material-icons">menu</IconButton>
			<Title>Palista</Title>
		</Section>
		<Section align="end" toolbar>
			<a href="/"><IconButton class="material-icons" aria-label="Home">home</IconButton></a>
			<a href="/about"><IconButton class="material-icons" aria-label="About">info</IconButton></a>
			<a href="/account/settings"
				><IconButton class="material-icons" aria-label="settings">settings</IconButton></a
			>
		</Section>
	</Row>
</TopAppBar>

<AutoAdjust {topAppBar}>
	<slot></slot>
</AutoAdjust>

<style>
	/* Hide everything above this component. */
	:global(#smui-app),
	:global(body),
	:global(html) {
		display: block !important;
		height: auto !important;
		width: auto !important;
		position: static !important;

		margin: 0;
		padding: 0;
	}
</style>
