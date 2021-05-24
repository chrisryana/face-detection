<script>
	let name = '<8@';
</script>

<h1 class="visually-hidden">Игра повтори эмоцию по картинке</h1>
<main class="content">
	<div class="row">
		<div class="column">
			<section class="card questions">
				<h2 class="questions__tagline">Вопрос 1</h2>
				<div class="questions__images">
					<div class="questions__image-wrapper">
						<img src="https://cs5.pikabu.ru/post_img/2015/10/09/4/1444367594_252211042.gif"
							alt="Кадр из фильма Дежурный папа, когда персонаж Эдди Мерфи оглядывает туалет после ребенка"
							class="questions__image" />
					</div>
					<div class="video-placeholder questions__image-wrapper"></div>
					<!-- <video id="video" width="312" height="250" autoplay muted></video> -->
				</div>
				<ul class="questions__answers">
					<li class="questions__answers-item answers-item">
						<button class="answers-item__button">вариант 1</button>
					</li>
					<li class="questions__answers-item answers-item">
						<button class="answers-item__button">вариант 2</button>
					</li>
					<li class="questions__answers-item answers-item">
						<button class="answers-item__button">вариант 3</button>
					</li>
					<li class="questions__answers-item answers-item">
						<button class="answers-item__button">вариант 4</button>
					</li>
				</ul>
			</section>
		</div>
		<div class="column">
			<section class="card timer">
				<h2 class="visually-hidden">Осталось:</h2>
				30 секунд
			</section>
			<section class="card rules">
				<h2 class="rules__tagline">Как играть?</h2>
			</section>
		</div>
	</div>
</main>

<!-- <div class="wrapper">
	<div class="loader">Распознаю твое личико (ಠ_ಠ)...</div>
	<video id="video" width="720" height="576" autoplay muted></video>
</div>
<script src="face-api.min.js"></script>
<script src="main.js"></script> -->

<style>
	body {
		margin: 0;
		padding: 0;
		font-family: Arial, sans-serif;
		font-size: 1rem;
	}

	* {
		box-sizing: border-box;
	}

	a {
		text-decoration: none;
	}

	img {
		max-width: 100%;
		height: auto;
	}

	ul, li {
		margin: 0;
		padding: 0;
		list-style: none;
	}

	.visually-hidden:not(:focus):not(:active),
	input[type="checkbox"].visually-hidden,
	input[type="radio"].visually-hidden {
		position: absolute;
		width: 1px;
		height: 1px;
		margin: -1px;
		border: 0;
		padding: 0;
		white-space: nowrap;
		clip-path: inset(100%);
		clip: rect(0 0 0 0);
		overflow: hidden;
	}

	.wrapper {
		padding: 20px;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.error, .loader {
		padding: 8px 20px;
		text-align: center;
		border-radius: 3px;
	}

	.error {
		background-color: #ffe9e9;
		color: #ff7171;
		border: 1px solid #ff7171;
	}

	.loader {
		opacity: 0.6;
		position: absolute;
		background-color: #e9ffeb;
		color: #34dc51;
		border: 1px solid #34dc51;
	}

	canvas {
		position: absolute;
	}

	.video-placeholder {
		display: inline-block;
		width: 312px;
		height: 250px;
		background-color: black;
	}

	.content {
		margin: 0 auto;
		max-width: 1200px;
		min-width: 885px;
		padding: 2.3%;
	}

	.row {
		display: flex;
	}

	.column {
		margin-right: 2.3%;
		flex-grow: 1;
	}

	.column:last-child {
		margin-right: 0;
	}

	.card {
		padding: 20px;
		border: 1px solid darkblue;
		border-radius: 3px;
		background-color: lightblue;
		margin-bottom: 15px;
	}

	.questions__images {
		display: flex;
		margin-bottom: 16px;
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