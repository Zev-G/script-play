<script lang="ts">
    import ScriptElementView from "./ScriptElementView.svelte";

    import type { ScriptElement } from "./TextProcessing";

    export let color = "black";
    export let content: ScriptElement[];
</script>

<div class="line-content" style:color={color}>
    {#each content as lineElement}
        <ScriptElementView element={lineElement} />
    {/each}
</div>

<style>
    .line-content {
        display: inline;
        /* align-content: ; */
    }
</style>