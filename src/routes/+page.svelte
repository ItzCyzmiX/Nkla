<script>
    import Header from "$lib/Header.svelte";
    import ImageInput from "$lib/ImageInput.svelte";
    import SolutionCard from "$lib/SolutionCard.svelte";

    let solutions = $state(false);
    let solving = $state(false);
    let solved = $state(false);

    const handleSolve = async (image) => {
        solving = true;

            solutions = {
                ex_1: {
                    q_1: "x = 2"
                },
                ex_2: {
                    q_1: "x = 2"
                }
            }
        
            solving = false;
            solved = true;
       
    };
</script>

<div class="min-h-screen bg-gray-50 text-gray-800 flex flex-col">
    <Header title="Gauth Homework Solver" />
    <main class="flex-1 p-6 space-y-6">
        {#if solving}
            <p class="text-center text-blue-500 text-lg animate-pulse">
                Solving...
            </p>
        {/if}

        {#if !solved}
            {#if !solving}
                <ImageInput on:solve={handleSolve} />
            {/if}
        {/if}

        {#if solutions}
            <div class="grid grid-cols-1 gap-4">

                <SolutionCard exs={solutions} />

            </div>
        {/if}
    </main>
</div>
