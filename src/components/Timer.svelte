<script>
  import { onMount, onDestroy } from 'svelte';
  import {STATE} from '../data/game';

  export const MAX_TIME_S = STATE.timer;
  export let time = MAX_TIME_S;
  let timer;

  const startTimer = () => {
    timer = setInterval(() => {
      if (time > 0) time -= 1;
      if (time === 0) clearInterval(timer)
    }, 1000)
  }


  onMount(() => {
		startTimer();
	});

	onDestroy(() => {
		clearInterval(timer);
	});

</script>


<section class="timer">
  <h2 class="visually-hidden">Таймер</h2>
  <span class="visually-hidden">Осталось</span>
  {time}
  <span class="visually-hidden">секунд</span>
</section>

<style>
  .timer {
    border-radius: 50%;
    background-color: #6BED03;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 150px;
    height: 150px;
    color: white;
    font-size: 24px;
    font-weight: bold;
  }
</style>