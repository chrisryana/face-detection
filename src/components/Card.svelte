<section class="card">
    <slot/>
</section>

<style>
    .card {
		padding: 40px;
		border-radius: 15px;
		background-color: rgba(255, 255, 255, 0.5);
		margin-bottom: 15px;
		background: linear-gradient(112.32deg, rgba(255, 255, 255, 0.7) 0%, rgba(255, 255, 255, 0) 101.12%);
		border-top: 1px solid rgba(255, 255, 255, 0.7);
		border-left: 1px solid rgba(255, 255, 255, 0.7);
		position: relative;
		box-shadow: 0 4px 4px rgba(0, 0, 0, .1), 0 1px 6px rgba(0, 0, 0, .05);
		backdrop-filter: blur(20px);
	}

	.card::after {
		content: "";
		position: absolute;
		width: 90%;
		height: 20px;
		bottom: -20px;
		right: 50%;
		transform: translateX(50%);
		background-color: #b0c1ef;
		z-index: -1;
		filter: blur(50px);
		-webkit-filter: blur(15px);
	}
</style>