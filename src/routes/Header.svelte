<script lang="ts">
    const {title} = $props();
    import * as m from "$lib/paraglide/messages"
</script>
<style>
    * {
        box-sizing: border-box;
        display: block;
    }
    header {
        background-color: var(--header-color);
    }
    h1 {
        padding-top: 10px;
        color: var(--slate-blue);
        text-align: center;
        font-size: 4vw;
    }
    nav {
        text-align: center;
        border-bottom: 1px solid var(--border);
        padding: 0 0.5rem 2rem 0.5rem;
        a {
            text-decoration: none;
            text-align: center;
            border: 1px solid;
            border-radius: 5px;
            color: var(--text);
            display: inline-block;
            padding: 0.1rem 1rem;
            text-decoration: none;
            &:hover {
                color: var(--primary-color);
            }
        }
    }

    @media only screen and (max-width: 720px) {
        h1 {
            font-size: 2.5rem;
        }
    }
</style>
<header>
    <h1>{title}</h1>
    <nav>
        <a href=".">{m.home()}</a>
    </nav>
</header>