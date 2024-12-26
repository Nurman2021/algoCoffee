<script>
import { onMount } from 'svelte';
import { Scene, PerspectiveCamera, WebGLRenderer, AmbientLight, DirectionalLight } from 'three';
import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader';
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';

let canvas;

onMount(() => {
  const scene = new Scene();
  const camera = new PerspectiveCamera(
    75,
    window.innerWidth / window.innerHeight,
    0.1,
    1000
  );
  camera.position.z = 5;

  const renderer = new WebGLRenderer({ canvas, antialias: true });
  renderer.setSize(window.innerWidth, window.innerHeight);

  const controls = new OrbitControls(camera, renderer.domElement);

  // Add lighting to the scene
  const ambientLight = new AmbientLight(0xffffff, 0.5); // Soft white light
  scene.add(ambientLight);

  const directionalLight = new DirectionalLight(0xffffff, 1); // Bright white directional light
  directionalLight.position.set(5, 10, 7.5); // Position the light
  scene.add(directionalLight);

  const loader = new GLTFLoader();
  let gltfScene;
  loader.load('/models/cup.glb', (gltf) => {
  	console.log(gltf);
    gltfScene = gltf.scene;
    scene.add(gltfScene);
  });

  function animate() {
    requestAnimationFrame(animate);

    controls.update();
    renderer.render(scene, camera);
  }

  animate();

  const handleResize = () => {
    camera.aspect = window.innerWidth / window.innerHeight;
    // camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
  };

  window.addEventListener('resize', handleResize);

  return () => {
    window.removeEventListener('resize', handleResize);
    renderer.dispose();
    controls.dispose();
  };
});
</script>

<canvas bind:this={canvas} style="display: block; width: 100vw; height: 100vh;"></canvas>
