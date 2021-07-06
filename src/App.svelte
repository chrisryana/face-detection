<script>
	import Description from './components/Description.svelte';
	import Question from './components/Question.svelte';
	import Result from './components/Result.svelte';
	import { QUESTIONS } from './data/questions';

	let questionIndex = -1;
	let rightAnswersCount = 0;

	function setNext() {
		questionIndex += 1;
	}

	function onRight() {
		rightAnswersCount += 1;
		setNext();
	}

	function reset() {
		questionIndex = -1;
	}
</script>

<h1 class="visually-hidden">Игра повтори эмоцию по картинке</h1>
<main class="content">
	{#if questionIndex < 0}
		<Description onStart={setNext}/>
	{/if}

	{#if questionIndex >= 0}
		<Question questionIndex={questionIndex} onRight={onRight} onEndTime={setNext}/>
	{/if}
	
	{#if questionIndex + 1 > QUESTIONS.length}
		<Result onBack={reset}/>
	{/if}
</main>

<style>
	.content {
		display: block;
		margin: 0 auto;
		max-width: 1200px;
		min-width: 885px;
		padding: 2.3%;
	}
</style>