<script>
    let username = "";
    let age = "";
    async function getAge() {
  fetch('https://api.agify.io/?name=' + username)
	.then((response) => response.json())
	.then((data) => {
  	username = data.name; // Path for name
  	age = data.age; // Path for age
	});
}
</script>
<h1>Guess Age</h1>

<form on:submit|preventDefault={getAge}>
    <label for="name">Name:</label>
    <input id="username" bind:value={username} type="text" />
    <button type="submit">Check</button>
</form>

<p>Age: {age}</p>