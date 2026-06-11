<script lang="ts">
    import type { PageData } from '../Rhosistance/$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { rhosistance } from '../Ohm.svelte';
    import * as m from '$lib/paraglide/messages';
    let rho: string = $state('');
    let gauge: string = $state('');
    let length: string = $state('');
    let rhoValue: number = $state(0);
</script>
<Header title={m.neat_red_cat_hope()} />
<div class="fields">
    <label for="resistivity">{m.lost_lower_hyena_embrace()} (Ω mm²/m):</label>
    <input bind:value={rho} type="text" name="resistivity" id="resistivity" class="input">
    <label for="length">{m.length()} (m):</label>
    <input bind:value={length} type="text" name="length" id="length" class="input">
    <label for="gauge">{m.section_cable()} (mm²):</label>
    <input bind:value={gauge} type="text" name="gauge" id="gauge" class="input">
    <button onclick={() => { rhoValue = rhosistance(rho, gauge, length); }}>{m.calcul()}</button>
    <p>Resistance: {rhoValue} Ω</p>
</div>
<div class="description">
    <p>{@html m.resistance_w_rho()}</p>
    <p><strong>R = ρ × (L / A)</strong></p>
    <p>{m.where()}</p>
    <ul>
        <li>{@html m.d_resistivity()}</li>
        <li>{@html m.d_length()}</li>
        <li>{@html m.d_gauge()}</li>
    </ul>
</div>