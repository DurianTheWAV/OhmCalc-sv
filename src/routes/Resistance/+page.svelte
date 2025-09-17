<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { resistance } from '../Ohm.svelte';
    let voltage: string = $state('');
    let intensity: string = $state('');
    let resistanceValue: number = $state(0)
    import * as m from '$lib/paraglide/messages';
</script>
<Header title={m.resistance()} />
<div class="fields">
    <label for="voltage">{m.voltage()} (V):</label>
    <input bind:value={voltage} type="text" name="voltage" id="voltage" class="input">
    <label for="intensity">{m.intensity()} (A):</label>
    <input bind:value={intensity} type="text" name="intensity" id="intensity" class="input">
    <button onclick={() => { resistanceValue = resistance(voltage, intensity); }}>{m.calcul()}</button>
    <p>Resistance: {resistanceValue} Ω</p>
</div>
<div class="description">
    <p>{@html m.minor_quaint_peacock_blend()}</p>
    <p><strong>R = V / I</strong></p>
</div>