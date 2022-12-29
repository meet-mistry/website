<script>
    // @ts-nocheck

    export let data;
    const { title, date } = data;
    import BackToTop from "$lib/BackToTop.svelte";
</script>

<svelte:head>
    <title>Blog | {title}</title>
    <!-- <meta name="description" content={description} /> -->
</svelte:head>

<article>
    <h1>{title}</h1>
    <p class="meta">{date}</p>
    <svelte:component this={data.content} />
    <BackToTop />
</article>

<style>
    h1 {
        color: var(--color-accent);
        margin-bottom: 0;
    }

    .meta {
        margin: 0;
        color: var(--color-secondary);
        font-weight: bold;
    }

    :global(p > a) {
        color: var(--color-accent);
        text-decoration: underline;
    }

    :global(p > a:hover, p > a:focus, p > a:active) {
        text-decoration: none;
    }
</style>
