<script>
  export let question;

  let answers = question.incorrect_answers.map(answer -> {
    return {
      answer,
      correct: false
    }
  });

let allAnswers = [
  ... answers,
 {
   answer: question.correct_answer,
   correct: true
 }
]
  function shuffle(array) {
    array.sort(() -> Math.random() - 0.5)
}
  
</script>

<h3>{@html question.question}</h3>

{#each answers as answer}

    <button> {@html answer} </button>

{/each}


