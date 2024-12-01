<script>
	function handleClick(e) {
		alert("I've been clicked!!!")
	}
</script>

<button on:click={handleClick}>
  Press me
</button>
    
<button on:click={() => console.log('I was pressed')}>
  Press me
</button>

<button on:click|once={handleClick}>
  Press me once!!!
</button>

<button on:submit|preventDefault={handleClick}>
  Press me
</button>
