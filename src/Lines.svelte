<script lang="ts">
    import type { Line } from "./TextProcessing";
    import Character from "./Character.svelte";
    import LineView from "./LineView.svelte";

    let colorMap = { 
        "CONSTANCE": "black",
        "DESDEMONA": "rgb(170, 31, 184)",
        "JULIET": "rgb(20 139 63)",
        "OTHELLO": "rgb(210 95 171)",
        "CHORUS": "rgb(170, 31, 184)",
        "ROMEO": "rgb(225, 11, 19)",
        "IAGO": "rgb(0 200 166)",
        "TYBALT": "rgb(202, 104, 234)",
        "MERCUTIO": "rgb(40 86 199)",
        "CLAUDE": "rgb(25 130 25)",
        "RAMONA": "rgb(78, 6, 246)",
        "STUDENT": "rgb(78, 6, 246)",
        "NURSE": "rgb(130, 145, 95)",
        "GHOST": "rgb(210 95 171)",
        "SERVANT": "rgb(130, 145, 95)",
        "SOLDIER": "rgb(78, 6, 246)",
        "CONSTANCE & DESDEMONA": "rgb(133 86 0)",
        "MERCUTIO & TYBALT": "rgb(133 86 0)",
        "JULIET & ROMEO": "rgb(133 86 0)",
        "ROMEO & JULIET": "rgb(133 86 0)",
        "DESDEMONA & JULIET": "rgb(133 86 0)",
    };

    export let lines: Line[];

</script>

<div class="lines-table">
    {#each lines as line}
        <Character name={line.character.text}/>
        <LineView content={line.line.children} color={colorMap[line.character.text]}/>
    {/each}
</div>

<style>
    .lines-table {
        display: grid;
        grid-template-columns: auto auto;
        align-items: baseline;
        row-gap: 2em;
        column-gap: 1em;
    }

    .lines-table :global(*) {
        font-size: 20px;
    }
</style>