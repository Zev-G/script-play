<script lang="ts">
    export let name: string;
</script>

<span class="character-name">
    {name}:
</span>

<style>
    .character-name {
        /* text-transform: capitalize; */
        font-family: serif;
        justify-self: end;
    }
</style>