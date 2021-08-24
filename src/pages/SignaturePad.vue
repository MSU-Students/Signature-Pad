<template>
  <h3 class="flex flex-center">Signature Pad</h3>
  <q-page>
    <q-card class="flex flex-center">
      <q-card-section>
        <q-form id="form-submit" method="POST">
          <div class="wrapper col self-start">
            <canvas
              id="signature-pad"
              class="signature-pad"
              width="400"
              height="200"
            ></canvas>
          </div>
          <q-card-actions align="right">
            <q-btn
              push
              color="secondary"
              class="btn btn-sm btn-secondary"
              label="Retry">
              </q-btn>
            <q-btn
              push
              color="secondary"
              class="btn btn-success"
              label="Submit"
            /> </q-card-actions></q-form
      ></q-card-section>
    </q-card>
  </q-page>
</template>
<script lang="ts">
import { Vue, Options } from 'vue-class-component';
@Options({
  components: {},
})
export default class SignaturePad extends Vue {
  
}
</script>
<style scoped>
 
body {
  max-width: 400px;
  margin: 0 auto;
  font-family: sans-serif;
  text-align: center;
}
.wrapper {
  position: relative;
  width: 400px;
  height: 200px;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
  border: solid 1px #ddd;
  margin: 10px 0px;
}
.signature-pad {
  position: absolute;
  left: 0;
  top: 0;
  width: 400px;
  height: 200px;
}
textarea {
  width: 100%;
  min-height: 100px;
}
   
  
</style>
