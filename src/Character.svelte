<script lang="ts">
    export let name: string;
</script>

<span class="character-name">
    {#if name.length != 0}
        {name}:
    {/if}
</span>

<style>
    .character-name {
        /* text-transform: capitalize; */
        font-family: serif;
        justify-self: end;
    }
</style>