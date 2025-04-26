<script>
	let zadania = [
		{ id: 1, nazwa: 'Kupić mleko', wykonane: false },
		{ id: 2, nazwa: 'Napisać raport', wykonane: true },
		{ id: 3, nazwa: 'Posprzątać dom', wykonane: false }
	];
</script>

<ul>
	{#each zadania as zadanie}
		<li class:wykonane={zadanie.wykonane}>
			{zadanie.nazwa}
		</li>
	{/each}
</ul>

<style>
	.wykonane {
		text-decoration: line-through;
		color: gray;
	}
</style>
