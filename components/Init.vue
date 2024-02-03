<template>
<TresCanvas window-size clear-color="orange">
    <TresPerspectiveCamera/>
    <OrbitControls/>
    <TresMesh :position="[0,1,0]" :scale="[1, 2, 0.5]" :rotation="[Math.PI / 3, 0, 0]">
    <TresBoxGeometry/>
    <TresMeshNormalMaterial/>
    </TresMesh>
    <TresAxesHelper />
    <TresGridHelper/>
</TresCanvas>
</template>

<script setup>
import { TresCanvas, useRenderLoop } from "@tresjs/core";
import { OrbitControls } from "@tresjs/cientos";
</script>