<template>
<TresCanvas window-size clear-color="orange">
    <TresPerspectiveCamera/>
    <OrbitControls/>
    <TresMesh :position="[0,0,0]" ref="cubeRef">
    <TresBoxGeometry />
    <TresMeshNormalMaterial/>
    </TresMesh>
    <TresAxesHelper />
    <TresGridHelper/>
</TresCanvas>
</template>

<script setup>
import { TresCanvas, useRenderLoop } from "@tresjs/core";
import { OrbitControls, useTweakPane } from "@tresjs/cientos";
import { shallowRef } from 'vue';

const { onLoop } = useRenderLoop()

const cubeRef = shallowRef()

onLoop(({delta, elapsed}) => {
    if(cubeRef.value) {
        cubeRef.value.rotation.y += delta
        cubeRef.value.rotation.z = elapsed

        cubeRef.value.position.y = Math.sin(elapsed * 2)

        cubeRef.value.scale.set(
            Math.sin(elapsed * 2),
            Math.sin(elapsed * 2),
            Math.sin(elapsed * 2),
        )
    }
})


watchEffect(() => {
    console.log({cubeRef})
})

</script>