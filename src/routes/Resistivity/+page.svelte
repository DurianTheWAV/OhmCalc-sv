<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { resistivity } from '../Ohm.svelte';
    let resistance:string = $state('');
    let gauge:string = $state('');
    let length:string = $state('');
    let rhoValue:number = $state(0);
    import * as m from '$lib/paraglide/messages';
</script>
<Header title={m.lost_lower_hyena_embrace()} />
<div class="fields">
    <label for="resistance">{m.resistance()} (Ω):</label>
    <input bind:value={resistance} type="text" name="resistance" id="resistance" class="input">
    <label for="gauge">{m.section_cable()} (mm²):</label>
    <input bind:value={gauge} type="text" name="gauge" id="gauge" class="input">
    <label for="length">{m.length()} (m):</label>
    <input bind:value={length} type="text" name="length" id="length" class="input">
    <button onclick={() => { rhoValue = resistivity(resistance, gauge, length); }}>{m.calcul()}</button>
    <p>{m.lost_lower_hyena_embrace()}: {rhoValue} Ω mm2/m</p>
</div>
<div class="description">
    <p>{@html m.resistivity()}</p>
    <p><strong>ρ = R × (A / L)</strong></p>
    <p>{m.where()}</p>
    <ul>
        <li>{@html m.d_resistance()}</li>
        <li>{@html m.d_gauge()}</li>
        <li>{@html m.d_length()}</li>
    </ul>
</div>