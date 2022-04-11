<script lang=ts>
    import DataMarkerView from "./DataMarkerView.svelte";
    import Lines from "./Lines.svelte";
    import { Line, ScriptElement } from "./TextProcessing";

    export let elements: ScriptElement[];

    let elementGrouping = [];
    let buffer = [];
    let type: string = "line";
    for (let element of elements) {
        const elementType = element instanceof Line ? "line" : "marker";
        if (elementType == type) {
            buffer.push(element);
        } else {
            if (buffer.length != 0) {
                elementGrouping = [...elementGrouping, {
                    type,
                    items: buffer
                }];
            }
            buffer = [element];
            type = elementType;
        }
    }
    if (buffer.length != 0) {
        elementGrouping = [...elementGrouping, {
            type,
            items: buffer
        }];
    }

</script>

{#each elementGrouping as group}
    {#if group.type == "line"}
        <Lines lines={group.items}/>
    {:else}
        <DataMarkerView text={group.items.map((item) => item.text.substring(1)).join(", ")}/>
    {/if}
{/each}