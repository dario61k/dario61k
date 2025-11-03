<script>
    import Header from "$lib/components/layout/header.svelte";
    import Footer from "$lib/components/layout/footer.svelte";
</script>

<svelte:head>
    <title>/blog</title>
    <meta
        name="description"
        content="Software Engineer specializing in Go, Rust, and modern web technologies"
    />
</svelte:head>

<Header />
<main>
    <section class="hero">
        <img src="/lainc.jpg" alt="lain pic" class="hero-img" />
        <h1>read my stuff</h1>
    </section>
</main>
<Footer />

<style>
    main {
        min-height: 100vh;
    }

    .hero {
        text-align: center;
        padding: 6.25rem 0 1.25rem 0;
    }

    .hero-img {
        width: 25rem;
        max-width: 80%;
        margin-bottom: 0.625rem;
        object-fit: cover;
    }

    @media (max-width: 48rem) {
        .hero {
            text-align: center;
            padding: 2.25rem 0 1.25rem 0;
        }
    }
</style>
