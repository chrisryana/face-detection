<script>
    import Base from '../layouts/Base.svelte';
    import Video from './Video.svelte';
    import { QUESTIONS } from '../data/questions';

    export let questionIndex;
</script>

<Base>
    <div class="questions__images">
        <div class="questions__image-wrapper">
            <img src={QUESTIONS[questionIndex].img}
                alt={QUESTIONS[questionIndex].alt}
                class="questions__image" />
        </div>
        <!-- <div class="video-placeholder questions__image-wrapper"></div> -->
        <!-- <video id="video" width="312" height="250" autoplay muted></video> -->
        <Video />
    </div>
    <ul class="questions__answers">
        {#each QUESTIONS[questionIndex].variants as { emotion, isCorrect }, i}
            <li class="questions__answers-item answers-item">
                <button class="answers-item__button">{emotion}</button>
            </li>
        {/each}
    </ul>
</Base>

<style>
    .video-placeholder {
		display: inline-block;
		width: 312px;
		height: 250px;
		background-color: black;
        border-radius: 10px;
	}

    .questions__images {
		display: flex;
		margin-bottom: 16px;
	}

    .questions__image {
        border-radius: 10px;
    }

	.questions__image-wrapper {
		flex-grow: 1;
	}

	.answers-item {
		margin-bottom: 10px;
	}

	.answers-item:last-child {
		margin-bottom: 0;
	}

	.answers-item__button {
		font-size: 1.3rem;
		display: block;
		width: 100%;
		padding: 6px 16px;
		border: none;
		border-radius: 3px;
	}

	.answers-item__button:hover {
		cursor: pointer;
		background-color: black;
		color: white;
	}
</style>