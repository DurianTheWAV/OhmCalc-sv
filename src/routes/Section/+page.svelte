<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { section } from '../Ohm.svelte';
    import * as m from '$lib/paraglide/messages';
    let raw_diameter: string = $state('');
    let gaugeValue: number = $state(0);
</script>

<Header title="Section"/>

<div class="fields">
    <label for="diameter">{m.diameter()} (mm):</label>
    <input bind:value={raw_diameter} type="text" name="diameter" id="diameter" class="input">
    <button onclick={() => { gaugeValue = section(raw_diameter); }}>{m.calcul()}</button>
    <p>{m.section_cable()}: {gaugeValue} mm2</p>
</div>

<div class="description">
    <p>{@html m.few_drab_seahorse_jolt()}</p>
    <p><strong>A = π × (d/2)²</strong></p>
    <p>{m.where()}</p>
    <ul>
        <li>{@html m.d_diameter()}</li>
    </ul>
</div>