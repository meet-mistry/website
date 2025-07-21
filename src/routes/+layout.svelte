<script>
    import { page } from "$app/state";
    import ThemeToggle from "$lib/ThemeToggle.svelte";
    import Transition from "$lib/PageTransition.svelte";
</script>

<nav>
    <a href="/">/home</a>
    <a href="/blog">/blog</a>
    <a href="/about">/about</a>
    <ThemeToggle />
</nav>

<main>
    <Transition url={page.url}>
        <slot />
    </Transition>
</main>

<style>
    nav a,
    nav a:visited,
    nav a:active {
        flex-wrap: wrap;
        font-weight: bold;
        font-family: var(--font-heading);
        margin-right: 0.8em;
        color: var(--color-text);
        text-decoration: none;
        box-shadow: 0 2px 0 0 var(--color-accent);
    }

    nav a:hover {
        box-shadow: none;
    }
</style>
