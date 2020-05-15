<template>
<Page actionBarHidden="true">
  <WebView class="test" src="https://challenge.48h.codes/map/" />
</Page>
</template>

<script lang="ts">
import { WebView } from "tns-core-modules/ui/web-view";
import { requestPermission, hasPermission } from 'nativescript-permissions';

  export default {
    data() {
      return {
      }
    },
    async created() {
      if (hasPermission(android.Manifest.permission.ACCESS_FINE_LOCATION)) {
        console.log('HAS PERMISSION !!')
      } else {
        console.log('REQUEST PERMISSION !!')
        await requestPermission(android.Manifest.permission.ACCESS_FINE_LOCATION, 'please')
        console.log('DONE')
      }
    }
  }
</script>

<style scoped>
.test {
  height: 100%;
  width: 100%;
  margin:0;
  padding:0;
}
</style>
