<script>
	import MyInput from "./MyInput.svelte"
	
	let value = "Svelte"
	let fillings = []
	let tortilla = ""
	let myDiv
</script>

<p>
	<MyInput bind:value={value} />
	<!-- Shorthand -->
	<MyInput bind:value />
</p>

<p>
	<select multiple bind:value={fillings}>
		<option value="Rice">Rice</option>
		<option value="Beans">Beans</option>
		<option value="Cheese">Cheese</option>
	</select>
</p>

<label>
	<input
		type="radio"
		bind:group={tortilla}
		value="Plain" />
	Plain
</label>
<label>
	<input
		type="radio"
		bind:group={tortilla}
		value="Whole wheat" />
	Whole wheat
</label>
<label>
	<input
		type="checkbox"
		bind:group={fillings}
		value="Rice" />
	Rice
</label>
<label>
	<input
		type="checkbox"
		bind:group={fillings}
		value="Beans" />
	Beans
</label>
<label>
	<input
		type="checkbox"
		bind:group={fillings}
		value="Cheese" />
	Cheese
</label>
<p>
	Type of tortilla: {tortilla}
</p>
<p>
	Selected fillings: {fillings.join(",")}
</p>

<div bind:this={myDiv}/>
<button on:click={() => myDiv.innerText = 'My text'}>
  Click
</button>
