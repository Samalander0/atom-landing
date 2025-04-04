<script>
  import '$lib/styles/landing.scss';

  import { Canvas } from '@threlte/core';
  import Scene from '$lib/components/Scene.svelte';

  import Metatags from '$lib/components/Metatags.svelte';
</script>

<Metatags/>

<main class="landing-main">
  <Canvas>
    <Scene />
  </Canvas>
  <div class="main-content">
    <div class="text">
      <h1>Oppenheimer<br/>Energy 2025</h1>
    </div>
  </div>
</main>