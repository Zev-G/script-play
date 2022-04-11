<script lang="ts">
    import { Italics, ScriptElement, StageQueue, ParentElement, PlainScriptElement } from "./TextProcessing";

    export let element: ScriptElement;

</script>

<div class="script-element">
    {#if element instanceof Italics}
        <span>{element.text}</span>
    {:else if element instanceof StageQueue}
        [<span class="stage-queue">{element.text.substring(1, element.text.length - 1)}</span>]
    {:else if element instanceof ParentElement}
        <span class="parent">
            {#each element.children as child}
                <svelte:self element={child} />
            {/each}
        </span>
    {:else if element instanceof PlainScriptElement}
        <span class="plain-text">
            {element.text}
        </span>
    {/if}
</div>

<style>
    * {
        font-family: serif;
    }

    .script-element {
        display: inline;
        margin: 0;
        padding: 0;
    }

    .stage-queue {
        font-style: italic;
    }
</style>