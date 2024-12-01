<!-- from https://levelup.video/tutorials/svelte-for-beginners/our-questions -->

<script>

let quiz = getQuiz();


async function getQuiz(){
  const res = await fetch("alink");
  const quiz = await res.json();
  return quiz;
}

function handleClick(){
  quiz = getQuiz();  
  }
</script>

<div>
  <button on:click={handleClick}> Get New Questions </button>

  {#await quiz}
    Loading...
  {:then data}
  <h3>{data.results[0].question}</h3>
  {#each data.results as question}
    <button on:click={() -> pickAnswer(answer)}> 
      Answer {answer.toUpperCase()} 
    </button>
  {/each}
  {/await}
  
