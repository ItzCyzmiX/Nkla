<script>
    import { onMount } from "svelte";

    export let exs = {};

</script>


    {#each Object.entries(exs) as [key, ex]}
    <div
    class="p-4 bg-white rounded-lg shadow-md hover:shadow-lg transition-shadow border-2 border-gray-700/50"
>
        <h1 class="text-blue-600 text-3xl font-bold">{key}</h1>
        {#each Object.entries(ex) as [qID, q]}
            <h1 class="text-blue-400 text-xl font-bold p-2">{qID}:</h1>
            <p class="text-gray-700 font-medium pl-4">{q}</p>
        {/each}
    </div>
    {/each}

