<script>
  import { Group } from 'three'
  import { T, forwardEventHandlers } from '@threlte/core'
  import { useGltf } from '@threlte/extras'

  export const ref = new Group()

  const gltf = useGltf('/models/cup.glb')

  const component = forwardEventHandlers()
</script>

<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
  {#await gltf}
    <slot name="fallback" />
  {:then gltf}
    <T.Group scale={5} position={[0, 1, 0]}>
      <T.Mesh
        geometry={gltf.nodes.Object_5.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.09, 0.3, 0.09]}
        rotation={[-0.06, -0.65, 0.23]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_7.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.11, 0.03, 0.11]}
        rotation={[0.49, -0.96, -0.15]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_9.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.18, 0.03, 0.1]}
        rotation={[-0.7, 0.79, 0.25]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_11.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.2, 0.03, 0.02]}
        rotation={[-0.79, 0.59, 0.51]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_13.geometry}
        material={gltf.materials.Marshmallow}
        position={[0.04, 0.3, 0.14]}
        rotation={[-1.39, 1.33, 1.74]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_15.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.14, 0.29, 0.01]}
        rotation={[0.16, 0.27, 0.07]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_17.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.08, 0.31, 0.02]}
        rotation={[3.13, -0.67, -2.4]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_19.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.13, 0.29, -0.08]}
        rotation={[-0.48, -1.04, -0.42]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_21.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.08, 0.3, -0.05]}
        rotation={[-2.43, 0.07, 3.13]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_23.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.03, 0.29, -0.15]}
        rotation={[-1.42, 1.26, 0.86]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_25.geometry}
        material={gltf.materials.Marshmallow}
        position={[0.04, 0.03, 0.18]}
        rotation={[-1.12, -0.4, 0.25]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_27.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.03, 0.03, 0.19]}
        rotation={[-2.15, 1.33, 1.74]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_29.geometry}
        material={gltf.materials.Marshmallow}
        position={[-0.13, 0.03, 0.18]}
        rotation={[-2.13, 1.33, 1.74]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_31.geometry}
        material={gltf.materials.Coffee}
        position={[0, 0.27, 0]}
        rotation={[-Math.PI, 1.03, -Math.PI]}
        scale={3.3}
      />
      <T.Mesh
        geometry={gltf.nodes.Object_33.geometry}
        material={gltf.materials.material}
        position={[0, 0.02, 0]}
        scale={3.3}
      />
      <T.Mesh geometry={gltf.nodes.Object_35.geometry} material={gltf.materials.Plate} scale={3.3} />
    </T.Group>
  {:catch error}
    <slot name="error" {error} />
  {/await}

  <slot {ref} />
</T>
