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
              <u>SIGNATURE PAD</u>
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
              style="height: 50px"
              class="bg-red-5 text-white"
              label="LOGIN"
              @click="login = true"
            />
            <br />

            <div class="separator text-weight-bold">or</div>
            <br />
            <q-btn
              class="bg-indigo text-white"
              style="height: 50px"
              label="SIGN UP"
              @click="signup = true"
            />
          </q-card-actions>
        </q-card>
      </div>
      <q-dialog v-model="signup" class="q-pm-lg">
        <q-card bordered>
          <q-card-title>
            <p class="text-italic q-ml-md"><u>insert your signature here.</u> </p>
          </q-card-title>
          <q-card-separator />
          <q-card-main>
            <div class="wrapper">
              <canvas
                id="canvas"
                style="border: 1px solid black; cursor: text"
                width="500px"
                height="400px"
              >
              </canvas>
            </div>
            <q-card-actions>
              <q-btn
                flat
                round
                class="absolute-top-right"
                color="indigo"
                icon="refresh"
              />
              <!-- <q-icon name="refresh" class="absolute-top-right" size="50px" />*/ -->
              <q-btn push color="indigo" label="Register" class="on-right" />
            </q-card-actions>
          </q-card-main>
        </q-card>
      </q-dialog>
      <q-dialog v-model="login" class="q-pm-lg">
        <q-card filled>
          <q-card-title>
            <p class="text-italic q-ml-md"><u>insert your signature here.</u> </p>
          </q-card-title>
          <q-card-separator />
          <q-card-main>
            <div class="wrapper">
              <canvas
                id="signature-pad"
                class="signature-pad"
                width="500px"
                height="400px"
              >
              </canvas>
            </div>
            <q-card-actions>
              <q-btn
                flat
                round
                class="absolute-top-right"
                color="indigo"
                icon="refresh"
              />
              <!-- <q-icon name="refresh" class="absolute-top-right" size="50px" /> -->
              <q-btn push color="red-5" label="Verify" class="on-right" />
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
  login = false;
  signup = false;
  slide = 'style';
  navPos = 'bottom';

 // A function called when mouse clicked on canva
//  canvas?.addEventListener("click", function(e));
}
</script>

<style scoped>
.page {
  background-image: url('~assets/SP.jpg');
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


