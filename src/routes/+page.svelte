<script>
    import Header from "$lib/components/layout/header.svelte";
    import Footer from "$lib/components/layout/footer.svelte";

    const svgIcons = {
        Email: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="icon icon-tabler icons-tabler-outline icon-tabler-mail"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M3 7a2 2 0 0 1 2 -2h14a2 2 0 0 1 2 2v10a2 2 0 0 1 -2 2h-14a2 2 0 0 1 -2 -2v-10z" /><path d="M3 7l9 6l9 -6" /></svg>`,
        Resumen: `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" class="icon icon-tabler icons-tabler-outline icon-tabler-file-smile"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M14 3v4a1 1 0 0 0 1 1h4" /><path d="M17 21h-10a2 2 0 0 1 -2 -2v-14a2 2 0 0 1 2 -2h7l5 5v11a2 2 0 0 1 -2 2zm-7 -7h.01m3.99 0h.01" /><path d="M10 17a3.5 3.5 0 0 0 4 0" /></svg>`,
    };

    const skillsData = {
        "Languages": [
            "Go",
            "Rust",
            "TypeScript",
            "JavaScript",
            "Python",
            "Bash",
            "SQL",
            "HTML",
            "CSS"
        ],
        "Data Bases": [
            "PostgreSQL",
            "MySql",
            "MariaDB",
            "Sqlite",
            "MongoDB",
            "Redis",
        ],
        "Frameworks and libraries": [
            "Gin",
            "Chi",
            "Express",
            "NestJS",
            "FastAPI",
            "Django",
            "React",
            "Svelte",
        ],
        "Tools": ["Git", "Docker", "Linux", "Apache", "Nginx"],
        "Cloud and Services": ["AWS", "Cloudflare", "Vercel", "Railway", "Render", "Netlify"],
    };
</script>

<svelte:head>
    <title>/dario61k</title>
    <meta
        name="description"
        content="Software Engineer specializing in Go, Rust, and modern web technologies"
    />
</svelte:head>

<Header />
<main>
    <section class="hero">
        <img src="/gatoc.jpg" alt="Darío's cat" class="hero-img" />
        <h1>Yo! I'm Darío</h1>
        <h2>A Software Engineer</h2>
    </section>

    <section class="block">
        <div class="block-content">
            <h2 class="fm">About me</h2>
            <p class="fs">
                Fullstack developer with a soft spot for <strong>Go</strong> and
                <strong>Rust</strong>. Currently working as a backend developer
                focused on distributed systems and cloud architecture. 
                Graduate from University of Computer Sciences (UCI) Havana, Cuba.
            </p>
            <div class="abme-butt">
                <a href="/cv/cv.pdf" download>
                    <button>{@html svgIcons["Resumen"]} Download CV</button>
                </a>
                <a href="mailto:dario61k@gmail.com" target="_blank">
                    <button>{@html svgIcons["Email"]} Email</button>
                </a>
            </div>
        </div>
    </section>

    <section class="block">
        <div class="block-content skills">
            <h2 class="fb">Skills</h2>
            {#each Object.entries(skillsData) as [category, techs]}
                <div class="skills-block">
                    <h3 class="fm">{category}</h3>
                    <div class="skills-grid">
                        {#each techs as tech}
                            <span class="fs">{tech}</span>
                        {/each}
                    </div>
                </div>
            {/each}
        </div>
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
        width: 15rem;
        height: 15rem;
        border-radius: 50%;
        margin-bottom: 0.625rem;
        object-fit: cover;
    }

    .hero h1 {
        font-size: 3rem;
    }

    .block {
        display: flex;
        justify-content: center;
        padding: 0.9375rem;
    }

    .block-content {
        width: 100%;
        max-width: 60rem;
    }

    .abme-butt {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .abme-butt button {
        background-color: rgba(255, 255, 255, 0.032);
        color: rgb(210, 210, 210);
        border: 1px solid rgba(255, 255, 255, 0.076);
        border-radius: 8px;
        padding: 8px;
        margin-top: 1rem;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
        display: flex;
        align-items: center;
        gap: 5px;
    }

    .abme-butt button:hover {
        background-color: rgba(95, 145, 123, 0.178);
    }

    .skills {
        margin-top: 5rem;
    }

    .skills h2 {
        text-align: center;
        margin-bottom: 2rem;
    }

    .skills-block {
        margin-bottom: 2rem;
    }

    .skills-block:last-child {
        margin-bottom: 0;
    }

    .skills-block h3 {
        margin-bottom: 1rem;
        font-size: 1.25rem;
        font-weight: 600;
    }

    .skills-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(10.5rem, 1fr));
        gap: 0.5rem;
    }

    .skills-grid span {
        background-color: rgba(240, 248, 255, 0.06);
        border: 1px solid rgba(143, 143, 143, 0.115);
        border-radius: 0.5rem;
        padding: 0.5rem 0rem;
        max-width: 11.5rem;
        text-align: center;
        font-weight: 500;
        transition: all 0.2s ease;
        cursor: pointer;
    }

    @media (max-width: 48rem) {
        .hero {
            padding: 4rem 1rem 1rem 1rem;
        }

        .hero h1 {
            font-size: 2rem;
        }

        .hero-img {
            width: 6rem;
            height: 6rem;
        }

        .skills-grid {
            grid-template-columns: repeat(auto-fit, minmax(6.25rem, 1fr));
            gap: 0.5rem;
        }

        .skills-grid span {
            padding: 0.375rem 0rem;
            font-size: 1rem;
        }
    }

    @media (max-width: 30rem) {
        .skills-grid {
            grid-template-columns: repeat(3.25rem, 1fr);
        }

        .hero h1 {
            font-size: 1.75rem;
        }
    }
</style>
