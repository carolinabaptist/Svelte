<!-- from https://levelup.video/tutorials/svelte-for-beginners/our-questions -->

<script>
import Question from "./Question.svelte";
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
  
    {#each data.results as question}
      <Question {question}/>
    {/each}
  {/await}
</div>
  
