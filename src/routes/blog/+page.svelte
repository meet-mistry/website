<script>
    // @ts-nocheck

    export let data;
</script>

<svelte:head>
    <title>Blog | Meet Mistry</title>
    <meta name="description" content="Personal blog" />
</svelte:head>

<main>
    <h1 class="page-title">Posts</h1>

    {#each data.posts as post}
        <h1>
            <a class="post-title" href={post.path}>
                {post.meta.title}
            </a>
        </h1>
        <p class="meta">{post.meta.date}</p>
        <p class="meta">{post.meta.description}</p>
    {/each}
</main>

<style>
    .post-title {
        color: var(--color-accent);
        text-decoration: none;
    }

    .meta {
        margin: 0;
        color: var(--color-secondary);
        font-weight: bold;
    }
</style>
