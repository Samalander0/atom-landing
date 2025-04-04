<script>
  import { onMount, onDestroy } from 'svelte';
  import { T, useTask  } from '@threlte/core';
  import { OrbitControls, Grid } from '@threlte/extras';

  let rotation = 0
  useTask((delta) => {
    rotation += delta
  })

  const ring_radius = 0.075,
        ring_spacing = 0.2,
        ring_offset = 3.5,
        ring_color = '#e5e5e5',
        nucleus_color = '#f5f5f5',
        electron_color = 'white',
        electron_radius = 0.3;
</script>

<T.PerspectiveCamera
  makeDefault
  position={[10, 10, 10]}
>
  <OrbitControls
    autoRotate={true}
    rotateSpeed={0.5}
    enableZoom={false}
  />
</T.PerspectiveCamera>

<!-- Lighting -->
<T.DirectionalLight
  position.y={10}
  position.z={10}
  intensity={5}
  castShadow={true}
/>
<T.AmbientLight intensity={1.5} />

<!-- Center -->
<T.Mesh>
  <T.SphereGeometry args={[1.75, 64, 64]} />
  <T.MeshStandardMaterial 
    color={nucleus_color} 
    metalness={0.1} 
    roughness={0.5} 
  />
</T.Mesh>


<!-- Rings -->
<T.Group rotation.x={Math.PI * (1 / 3)} rotation.z={rotation}>
  <T.Mesh >
    <T.TorusGeometry args={[ring_offset, 0.075, 64, 64]} />
    <T.MeshStandardMaterial 
      color={ring_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh >

  <T.Mesh position.y={-ring_offset}>
    <T.SphereGeometry args={[electron_radius, 64, 64]} />
    <T.MeshStandardMaterial 
      color={electron_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh>
</T.Group>

<T.Group rotation.x={Math.PI * (2 / 3)} rotation.z={rotation + Math.PI * (1 / 4)}>
  <T.Mesh >
    <T.TorusGeometry args={[ring_offset + ring_spacing, 0.075, 64, 64]} />
    <T.MeshStandardMaterial 
      color={ring_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh >

  <T.Mesh position.y={ring_offset + ring_spacing}>
    <T.SphereGeometry args={[electron_radius, 64, 64]} />
    <T.MeshStandardMaterial 
      color={electron_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh>
</T.Group>

<T.Group rotation.z={rotation + Math.PI * (1 / 2)}>
  <T.Mesh>
    <T.TorusGeometry args={[ring_offset + 2 * ring_spacing, 0.075, 64, 64]} />
    <T.MeshStandardMaterial 
      color={ring_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh >

  <T.Mesh position.y={ring_offset + 2 * ring_spacing}>
    <T.SphereGeometry args={[electron_radius, 64, 64]} />
    <T.MeshStandardMaterial 
      color={electron_color} 
      metalness={0.1} 
      roughness={0.5} 
    />
  </T.Mesh>
</T.Group>