<script lang="ts">
    import type { PageData } from './$types';
    let { data }: { data: PageData } = $props();
    import Header from '../Header.svelte';
    import { serial_resistor } from '../Ohm.svelte';
    import * as m from '$lib/paraglide/messages';
    let resistor_list: string = $state('');
    let totalValue: number = $state(0);
</script>
<Header title={m.serial()} />
<div class="fields">
    <label for="resistor_list">{m.resistor_l()}</label>
    <input bind:value={resistor_list} type="text" name="resistor_list" id="resistor_list" class="input">
    <button onclick={() => { totalValue = serial_resistor(resistor_list.split(',')); }}>{m.calcul()}</button>
    <p>{m.total_resistance()}: {totalValue} Ω</p>
</div>
<div class="description">
    <p>{@html m.serial_r()}</p>
    <p><strong>R<sub>total</sub> = R<sub>1</sub> + R<sub>2</sub> + ... + R<sub>n</sub></strong></p>
    <p>{m.where()}</p>
    <ul>
        <li>{@html m.d_r_list()}</li>
    </ul>
</div>