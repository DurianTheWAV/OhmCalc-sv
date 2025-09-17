<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { voltage } from '../Ohm.svelte';
    let resistance: string = $state('');
    let intensity: string = $state('');
    let voltageValue: number = $state(0)
    import * as m from '$lib/paraglide/messages';
</script>
<Header title={m.voltage()}/>
<div class="fields">
    <label for="resistance">{m.resistance()} (Ω):</label>
    <input bind:value={resistance} type="text" name="resistance" id="resistance" class="input">
    <label for="intensity">{m.intensity()} (A):</label>
    <input bind:value={intensity} type="text" name="intensity" id="intensity" class="input">
    <button onclick={() => { voltageValue = voltage(resistance, intensity); }}>{m.calcul()}</button>
    <p>{m.voltage()}: {voltageValue} V</p>
</div>
<div class="description">
    <p>{@html m.front_calm_anaconda_pick()}</p>
    <p><strong>V = R × I</strong></p>
</div>