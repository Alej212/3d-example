<template>
  <TresCanvas window-size clear-color="black">
    <TresPerspectiveCamera/>
    <OrbitControls/>
    <TresMesh ref="sphereRef">
      <TresSphereGeometry></TresSphereGeometry>
      <TresMeshNormalMaterial></TresMeshNormalMaterial>
    </TresMesh>
    <TresGridHelper/>
  </TresCanvas>
</template>

<script setup>
import { TresCanvas, useRenderLoop } from "@tresjs/core";
import { OrbitControls } from "@tresjs/cientos";
//import {  } from "@tresjs/post-processing";

const sphereRef = ref()

const { onLoop } = useRenderLoop()

onLoop(({elapsed}) => {
  if (sphereRef.value) {
    sphereRef.value.position.y = Math.sin(elapsed)
  }
})

</script>
