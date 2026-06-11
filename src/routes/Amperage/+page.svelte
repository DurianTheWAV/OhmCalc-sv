<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { amperage } from '../Ohm.svelte';
    let voltage: string = $state('');
    let resistance: string = $state('');
    let amperageValue: number = $state(0);
    import * as m from '$lib/paraglide/messages';
</script>
<Header title={m.intensity()}/>
<div class="fields">
<label for="voltage">{m.voltage()} (V):</label>
<input bind:value={voltage} type="text" name="voltage" id="voltage" class="input">
<label for="resistance">{m.resistance()} (Ω):</label>
<input bind:value={resistance} type="text" name="resistance" id="resistance" class="input">
<button onclick={() => { amperageValue = amperage(voltage, resistance); }}>{m.calcul()}</button>
<p>{m.intensity()}: {amperageValue} A</p>
</div>
<div class="description">
    <p>{@html m.lazy_home_samuel_explore()}</p>
    <p><strong>I = V / R</strong></p>
</div>