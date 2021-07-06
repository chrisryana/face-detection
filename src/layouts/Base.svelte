<script>
    import Card from '../components/Card.svelte';
</script>

<div class="row">
    <div class="column">
        <Card>
            <slot/>
        </Card>
    </div>
    <!-- <div class="column">
			<section class="card timer">
				<h2 class="visually-hidden">Осталось:</h2>
				30 секунд
			</section>
			<section class="card rules">
				<h2 class="rules__tagline">Как играть?</h2>
			</section>
		</div> -->
</div>

<style>
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
</style>