<script lang="ts">
	import Card, { Content, PrimaryAction, Actions, ActionButtons, ActionIcons } from '@smui/card';
	import Button, { Label } from '@smui/button';
	import LayoutGrid, { Cell } from '@smui/layout-grid';
	import IconButton from '@smui/icon-button';
	let counter = 0;
</script>

<LayoutGrid>
	<Cell span={12}>
		<div class="title-bar">
			<h1>Lists</h1>
			<div class="btn-group-container">
				<Button variant="outlined">
					<Label>Add New</Label>
				</Button>
				<IconButton class="material-icons" aria-label="More">more_vert</IconButton>
			</div>
		</div>
	</Cell>
	<Cell span={12}>
		<p>
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum accusamus minus voluptatibus,
			rerum totam ratione repellat deserunt, asperiores explicabo laboriosam vitae libero nulla
			maxime facilis mollitia Laboriosam?
		</p>
		<p>
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Harum accusamus minus voluptatibus,
			rerum totam ratione repellat deserunt.
		</p>
	</Cell>
	{#each Array(9) as _unused, i}
		<Cell spanDevices={{ desktop: 3, tablet: 4, phone: 12 }}>
			<Card>
				<Content>count: {counter}</Content>
				<Actions>
					<Button on:click={() => counter++}>
						<Label>Increment</Label>
					</Button>
					<Button on:click={() => counter--}>
						<Label>Decrement</Label>
					</Button>
				</Actions>
			</Card>
		</Cell>
	{/each}
</LayoutGrid>

<style lang="scss">
	.title-bar {
		display: flex;
		align-items: center;
		justify-content: space-between;

		.btn-group-container {
			display: flex;
			align-items: center;
		}
	}

	// @media (min-width: 840px) {
	// .title-bar {
	// 	display: flex;
	// 	align-items: center;
	// 	justify-content: space-between;

	// 	.btn-group-container {
	// 		display: flex;
	// 		align-items: center;
	// 	}
	// }
	// }
</style>
