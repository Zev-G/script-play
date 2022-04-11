<script lang="ts">
    export let text: string;
</script>

<div class="data-marker">
    {text}
</div>

<style>
    .data-marker {
        font-size: 20px;
        font-family: serif;
        font-weight: bold;
        margin: 1.5em 0;
        text-align: center;
        width: 100%;
        border-bottom: 1px solid black;
    }
</style>