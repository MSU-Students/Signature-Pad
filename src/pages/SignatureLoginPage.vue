<template>
  <q-page class="page">
    <div class="row">
      <div class="col-6"></div>
      <div class="col-6 q-pt-xl">
        <q-card
          bordered
          class="q-ml-xl q-mr-xl bg-amber-2 q-pa-lg full-height"
          style="border-radius: 30px"
        >
          <q-card-section class="q-gutter-lg-md">
            <div class="text-h4 text-bold text-italic text-center q-mb-xl">
              SIGNATURE PAD
            </div>
            <div>
              <q-input
                v-model="text"
                color="deep-orange-11"
                type="text"
                label="Full Name"
              />
            </div>
          </q-card-section>

          <q-card-section> </q-card-section>

          <q-card-actions class="q-pr-md q-pl-md" vertical>
            <q-btn
              rounded
              style="height: 50px"
              class="bg-red-5 text-white"
              label="LOGIN"
            />
            <br />

            <div class="separator">or</div>
            <br />
            <q-btn
              class="bg-indigo text-white"
              rounded
              style="height: 50px"
              label="SIGN UP"
              @click="signup = true"
            />
          </q-card-actions>
        </q-card>
      </div>
      <q-dialog v-model="signup">
        <q-card class="q-ma-lg bg-red">
          <q-card-title>
             <p class="text-italic ">insert your signature here.</p> 
             </q-card-title>
          <q-card-separator />
          <q-card-main>
            <div class="wrapper">
              <canvas
                id="signature-pad"
                class="signature-pad"
                width="400"
                height="300"
              ></canvas>
            </div>
            <q-card-actions>
               <q-btn push color="indigo" label="Verify" class="on-right"/>
            </q-card-actions>
          </q-card-main>
        </q-card>
      </q-dialog>
    </div>
  </q-page>
</template>

<script lang="ts">
import { Vue, Options } from 'vue-class-component';
@Options({
  components: {},
})
export default class SignatureLoginPage extends Vue {
  text = '';
  signup = false;
  slide = 'style';
}
</script>

<style scoped>
.page {
  background-image: url('~assets/BG.jpg');
}
.separator {
  display: flex;
  align-items: center;
  text-align: center;
}
.separator::before,
.separator::after {
  content: '';
  flex: 1;
  border-bottom: 3px double #0e0d0d;
}
.separator::before {
  margin-right: 0.5em;
}
.separator::after {
  margin-left: 0.5em;
}
.wrapper {
  position: relative;
  width: 400px;
  height: 200px;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.signature-pad {
  position: absolute;
  left: 0;
  top: 0;
  width: 400px;
  height: 200px;
  background-color: white;
}
</style>
