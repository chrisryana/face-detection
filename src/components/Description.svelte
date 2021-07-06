<script>
	import Base from '../layouts/Base.svelte';

    export let onStart;
</script>

<Base>
    <h2 class="quiz-name">Эмоциональный квиз</h2>
    <div class="description">
        Привет! Предлагаю тебе повторить эмоцию за популярными персонажами разных фильмов и мультфильмов.
        Что нужно делать?
        <ol>
            <li>Для начала разреши своему браузеру доступ к камере.</li>
            <li>
                Здесь должно отобразиться твое лицо. Функция отслеживания под рамкой покажет какую эмоцию ты сейчас испытываешь.
                <div class="video-placeholder questions__image-wrapper"></div>
                <!-- <video id="video" width="312" height="250" autoplay muted></video> -->
            </li>
            <li>Я буду показывать кадр из фильма, а тебе нужно будет повторить выражение лица персонажа.</li>
            <li>Если ты показал правильную эмоцию, автоматически происходит переход к следующему вопросу.</li>
            <li>Всего 10 вопросов, на каждый отводится 15 секунд.</li>
        </ol>
        <p>
            В конце покажу твой результат.
            <br/>
            <span>Удачи!</span>
        </p>
        <button on:click={onStart}>
            Старт
        </button>
    </div>
</Base>

<style>

	.quiz-name {
        font-family: 'Open Sans', Arial, sans-serif;
        font-size: 5rem;
		font-weight: 800;
		letter-spacing: -4px;
		text-transform: uppercase;
        text-align: center;
        color: #f35626;
        background-image: -webkit-linear-gradient(92deg, #f35626, #feab3a);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: hue 10s infinite linear;
    }

    .description {
        padding: 0 30px;
        text-align: center;
    }

    @keyframes hue {
        from {
            -webkit-filter: hue-rotate(0deg);
        }
        to {
            -webkit-filter: hue-rotate(-360deg);
        }
    }
</style>