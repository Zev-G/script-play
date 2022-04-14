<script lang="ts">
    import { script, ScriptElement } from "./TextProcessing";
    import process from "./TextProcessing";
    import ScriptView from "./ScriptView.svelte";

    const elements: ScriptElement[] = process(script);
    
</script>


<ScriptView elements={elements}/>
<div class="center">
    <img alt="the end" src="/the-end.jfif">
</div>

<style>
    img {
        margin: 1em;
    }

    .center {
        display: flex;
        justify-content: center;
    }
</style>