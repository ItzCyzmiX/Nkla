<script>
    import { createEventDispatcher } from 'svelte';
    import Camera from './Camera.svelte';
  
    const dispatch = createEventDispatcher();
  
    const handleUpload = () => {
      const dummyImage = 'example-image.jpg';
      dispatch('solve', dummyImage);
    };
  </script>
  
  <div class="max-w-md mx-auto p-6 border rounded-lg shadow-md bg-gradient-to-r from-blue-50 to-white">
    <h2 class="text-xl font-semibold text-gray-800 text-center mb-4">
      Solve Your Math Problem
    </h2>
    <p class="text-sm text-gray-600 text-center mb-6">
      Upload or capture an image of your math problem, and we'll solve it for you!
    </p>
  
    <div class="flex flex-col items-center space-y-4">

    <Camera/>

    </div>
  </div>
  