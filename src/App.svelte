<script>
	const factions = ["Nordic", "Saxony", "Polania", "Crimea", "Rusviet"];
	const playerMats = [
		"Mechanical",
		"Industrial",
		"Agricultural",
		"Engineering",
		"Patriotic",
	];

	let factionIndices = [4, 0, 3, 1, 2];
	let playerMatIndices = [4, 2, 3, 1, 0];
	let results = [];

	for (let i = 0; i < 5; i++) {
		const factionLen = factionIndices.length;
		const playerMatLen = playerMatIndices.length;
		let faction;
		let playerMat;
		let factionSelection;
		let playerMatSelection;

		do {
			factionSelection = Math.floor(Math.random() * factionLen);
			playerMatSelection = Math.floor(Math.random() * playerMatLen);

			faction = factions[factionIndices[factionSelection]];
			playerMat = playerMats[playerMatIndices[playerMatSelection]];
			console.log({ faction, playerMat });
		} while (
			(faction === "Rusviet" && playerMat === "Industrial") ||
			(faction === "Crimea" && playerMat === "Patriotic")
		);

		results.push({ faction, playerMat });
		factionIndices = factionIndices.filter((val, i) => i !== factionSelection);
		playerMatIndices = playerMatIndices.filter(
			(val, i) => i !== playerMatSelection
		);

		console.log({ factionIndices });
	}
</script>

<style>
	.page-wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	h1 {
		text-align: center;
	}
	ol {
		padding: 0;
	}
</style>

<div class="page-wrapper">
	<h1>Faction / <br />Player Mat <br />Combinations</h1>

	<ol>
		<li>{results[0].faction}—{results[0].playerMat}</li>
		<li>{results[1].faction}—{results[1].playerMat}</li>
		<li>{results[2].faction}—{results[2].playerMat}</li>
		<li>{results[3].faction}—{results[3].playerMat}</li>
		<li>{results[4].faction}—{results[4].playerMat}</li>
	</ol>
</div>
