<script>
    import EasyCamera from "@cloudparker/easy-camera-svelte";
    import { onMount } from "svelte";

    let width = 300;
    let camera;
    let mirrorDisplay = true;

    const handleImage = async () => {
        let imageData = await camera.captureImage();
        const link = document.createElement("a");
        link.href = imageData;
        link.download = "homework.png";
        link.click();
    };
</script>

<div>
    <EasyCamera
        bind:width
        style="border-radius:5px; height: 400px"
        bind:this={camera}
        autoOpen
        bind:mirrorDisplay
    />
</div>

<button
    aria-label="take picture"
    class="relative w-16 h-16 rounded-full bg-red-500 hover:bg-red-600 focus:outline-none focus:ring-2 focus:ring-red-300 transition-colors duration-200 ease-in-out"
    type="button"
    onclick={handleImage}
>
    <div
        class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-8 h-8 bg-white rounded-full"
    ></div>
</button>
