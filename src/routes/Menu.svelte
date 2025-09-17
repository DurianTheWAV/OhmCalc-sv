<style>
    ul {
        list-style: none;
        padding: 0;
        margin-top: 10px;
        margin-bottom: 30px;
        text-align: center;
    }
    
    li {
        display: block;
        margin: 0;
    }
    
    a {
        text-decoration: none;
        text-align: center;
        display: inline-block;
        color: var(--primary-color);
        padding: 0px;
        &:hover {
            text-decoration: none;
            color: var(--secondary-color);
        }
    }

    h3 {
        margin-top: 20px;
        margin-bottom: 0px;
        font-size: 1.2rem;
        text-align: center;
        color: var(--border);
    }
</style>
<script>
    import * as m from "$lib/paraglide/messages"
</script>

<h3>{m.section_1()}</h3>
<ul>
    <li><a href="./Voltage">{m.voltage()}</a></li>
    <li><a href="./Amperage">{m.intensity()}</a></li>
    <li><a href="./Resistance">{m.resistance()}</a></li>
</ul>

<h3>{m.section_2()}</h3>
<ul>
    <li><a href="./Section">Section</a></li>
    <li><a href="./Resistivity">{m.lost_lower_hyena_embrace()}</a></li>
    <li><a href="./Rhosistance">{m.neat_red_cat_hope()}</a></li>
</ul>

<h3>{m.section_3()}</h3>
<ul>
    <li><a href="./Parallel">{m.parallel()}</a></li>
    <li><a href="./Serial">{m.serial()}</a></li>
</ul>