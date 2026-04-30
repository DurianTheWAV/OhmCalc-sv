<style>
    footer {
        box-sizing: border-box;
        display: flex;
        justify-content: center;
        align-items: flex-end;
        display: grid;
        grid-column: 2;
        margin-top: 4rem;
        padding: 2rem 1rem 1.5rem 1rem;
        font-size: 0.9rem;
        text-align: center;
        img {
            width: auto;
            height: 50px;
            padding-bottom: 5px;
        }
        h3 + a {
            display: block;
            padding-bottom: 10px;
        }
        
        h3 + a + a {
            display: block;
            padding-bottom: 10px;
        }
        p {
            margin: 0;
        }
    }
</style>
<script>
    import * as m from "$lib/paraglide/messages"
</script>
<footer>
    <div id="links">
        <h3>{m.liens()}</h3>
        <a href="https://github.com/DurianTheWAV/OhmCalc-sv"><img src="/github.svg" alt="Github"></a>
        <a href="https://ko-fi.com/L3L11A3Z1N" target="_blank"><img height="36" style="border:0px;height:36px;" src="https://storage.ko-fi.com/cdn/kofi3.png?v=6" alt="Buy Me a Coffee at ko-fi.com"></a>
    </div>
    <div id="copyright">
        <p>Made with ❤️ by <a href="https://github.com/DurianTheWAV/">DurianTheWAV</a> in Switzerland</p>
        <p>© 2025-2026 OhmCalc-sv</p>
    </div>
</footer>