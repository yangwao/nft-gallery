<template>
  <a-scene>
    <a-assets id="assets">
      
    </a-assets>

    <!-- 3d Models -->

 <!-- <a-gltf-model scale="90 90 90"
        gltf-model="https://cdn.glitch.me/af8eb8bf-2d48-4e54-a9b4-65d5c6a2e8dd/Ice_KodaGallery%20New%204k.glb?v=1640005593732" visible=""
        rotation="0 -92.0743176775233 0">
        </a-gltf-model>  -->

    <a-entity position="15.70262 -0.9575 -2.54031" visible=""
        rotation="0 -92.0743176775233 0">
        <a-entity v-if="id" :arrange-nft="formatedId">
        </a-entity>
    </a-entity>

    <!-- Camera Rig -->
    <a-entity id="cameraRig">
        <!-- position="0 8 0" -->
        <a-entity id="head" camera wasd-controls="acceleration:500" look-controls position="-65 20 80">
        </a-entity>

    </a-entity>

</a-scene>
</template>

<script lang="ts" >
import { Component, Prop, Vue } from 'nuxt-property-decorator'
import { NFT } from '../rmrk/service/scheme';

@Component({})
export default class Base extends Vue {
  public space = 'https://cdn.glitch.me/6d877418-2a34-48a1-b3eb-2cc2670deeef%2FGlb1.glb?v=1636762271679'
  private value2: any;
  @Prop({ type: Array, required: true }) public nfts!: NFT[];
  @Prop(String) public id!: string;

  get formatedId(): string {
    return `issuer: ${this.id}`
  }


}
</script>
