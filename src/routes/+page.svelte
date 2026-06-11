<title>OhmCalc</title>
<script lang='ts'>
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from './Header.svelte';
    import Menu from './Menu.svelte';
    import '../styles/global.css';
    import * as m from "$lib/paraglide/messages";
</script>

<Header title="OhmCalc"/>
<Menu />
<div class="description">
    <p>{m.description()}</p>
</div>