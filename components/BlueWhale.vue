<!-- <script setup>
import { TresCanvas } from '@tresjs/core'
import { useFBX, OrbitControls } from '@tresjs/cientos'

const model = await useFBX('/BlueWhalemodelcolored.fbx')

console.log(model)
</script>

<template>
  <TresCanvas window-size clear-color="#1F90FF">
    <TresPerspectiveCamera :position="[0,0,40]" />
    <OrbitControls />
    <Suspense>
      <primitive
        :object="model"
        :scale="0.025"
      />
    </Suspense>
    <TresDirectionalLight
    />
    <TresAmbientLight :intensity="1" />
  </TresCanvas>
</template> -->

<script setup lang="ts">
import { TresCanvas } from '@tresjs/core'
import { FBXModel, OrbitControls } from '@tresjs/cientos'
</script>

<template>
  <TresCanvas window-size clear-color="#1F90FF">
    <TresPerspectiveCamera :position="[0, 0, 15]" />
    <OrbitControls />
    <Suspense>
      <FBXModel
        path="/BlueWhalemodelcolored.fbx"
        :scale="0.030"
      />
    </Suspense>
    <TresDirectionalLight
      :intensity="2"
      :position="[3, 3, 3]"
    />
    <TresAmbientLight />
  </TresCanvas>
</template>