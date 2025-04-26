<script>
	async function fetchData() {
	  const [user, posts] = await Promise.all([
		fetch('https://api.example.com/user').then(res => res.json()),
		fetch('https://api.example.com/posts').then(res => res.json())
	  ]);
	  return { user, posts };
	}
  
	let dataPromise = fetchData();
  </script>
  
  {#await dataPromise}
	<p>Ładowanie danych...</p>
  {:then { user, posts }}
	<h1>Witaj, {user.name}!</h1>
	<h2>Ostatnie posty:</h2>
	<ul>
	  {#each posts as post}
		<li>{post.title}</li>
	  {/each}
	</ul>
  {:catch error}
	<p style="color: red;">Błąd: {error.message}</p>
  {/await}