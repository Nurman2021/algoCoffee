<script>
  import { T } from '@threlte/core'
  import { ContactShadows, Float, Grid, OrbitControls } from '@threlte/extras'
  import Cup from './models/cup.svelte'
</script>

<T.PerspectiveCamera
  makeDefault
  position={[-10, 10, 2]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableZoom={false}
    enableDamping
    autoRotateSpeed={1}
    target.y={1.5}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={0.9}
  position.x={5}
  position.y={10}
/>
<T.AmbientLight intensity={0.2} />

<!-- <ContactShadows
  scale={10}
  blur={2}
  far={2.5}
  opacity={0.8}
/> -->

<Cup/>