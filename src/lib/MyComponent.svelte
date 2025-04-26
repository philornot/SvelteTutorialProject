<script>
	let a = 0;
	let b = 0;
	let znak = '=';
	const specjalnyZnak = 'excuse me wtf?!'

	$: {
		if (a < b) {
			znak = '<';
		} else if (a === b) {
			znak = '=';
		} else if (a > b) {
			znak = '>'
		} else {
			znak = specjalnyZnak;
		}
	}
</script>
<h1>Numero Porównywaczo Inator</h1>
<p>a=<input placeholder="0" type="number" bind:value={a} /></p>
<p>b=<input placeholder="0" type="number" bind:value={b} /></p>

{#if znak != specjalnyZnak}
	<p>{a} {znak} {b}</p>
{:else}
	<p>{znak}</p>
{/if}
