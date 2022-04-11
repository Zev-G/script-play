<script lang="ts">
    import { script, ScriptElement } from "./TextProcessing";
    import process from "./TextProcessing";
    import ScriptView from "./ScriptView.svelte";
    import { onMount } from "svelte";

    const elements: ScriptElement[] = process(script);

    onMount(() => {
        document.onkeydown = keyDown;
    });

    function keyDown(event) {
        if (event.code == "ArrowLeft") {
            console.log("up");
        } else if (event.code == "ArrowRight") {
            console.log("down");
        }
    }
    
</script>


<ScriptView elements={elements}/>

<style>

</style>