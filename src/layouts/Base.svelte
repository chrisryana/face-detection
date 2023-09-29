<script>
    import Card from '../components/Card.svelte';
    import Timer from '../components/Timer.svelte';
</script>

<div class="row">
    <div class="column">
        <Card>
            <slot/>
        </Card>
    </div>
    <aside class="column">
        <Timer onEnd={() => {}}/>
        <section class="card rules">
            <h2 class="rules__tagline">Как играть?</h2>
        </section>
    </aside>
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