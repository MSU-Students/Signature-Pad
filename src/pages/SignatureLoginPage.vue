<template>
  <q-page class="q-pa-xl">
    <div class="row">
      <div class="col-6"></div>
      <div class="col-6">
        <q-card
          color="orange-11"
          class="my-card bg-amber-2 flex flex-center"
          bordered
          rounded
          outlined
          style="width: 45%; height: 500px"
        >
          <div style="width: 400px">
            <q-card-section class="q-gutter-y-md">
              <h3 class="Italic">Signature Pad</h3>
              <q-input color="red-11" v-model="text" label="Name" />
            </q-card-section>
            <q-card-actions class="q-gutter-y-md">
              <q-btn color="red-11" class="full-width" label="LOG-IN" />

              <q-btn color="indigo-10" class="full-width" label="SIGN-UP">
                <q-popup-proxy>
                  <q-banner>
                    <div class="q-pa-md">
                      <div class="q-gutter-md">
                        <q-carousel
                          v-model="carousel.slide"
                          transition-prev="scale"
                          transition-next="scale"
                          swipeable
                          animated
                          control-color="white"
                          navigation
                          padding
                          arrows
                          height="300px"
                          class="bg-primary text-white shadow-1 rounded-borders"
                        >
                          <q-carousel-slide
                            name="style"
                            class="column no-wrap flex-center"
                          >
                            <q-icon name="style" size="56px" />
                            <div class="q-mt-md text-center">
                              {{ carousel.lorem }}
                            </div>
                          </q-carousel-slide>
                          <q-carousel-slide
                            name="tv"
                            class="column no-wrap flex-center"
                          >
                            <q-icon name="live_tv" size="56px" />
                            <div class="q-mt-md text-center">
                              {{ carousel.lorem }}
                            </div>
                          </q-carousel-slide>
                          <q-carousel-slide
                            name="layers"
                            class="column no-wrap flex-center"
                          >
                            <q-icon name="layers" size="56px" />
                            <div class="q-mt-md text-center">
                              {{ carousel.lorem }}
                            </div>
                          </q-carousel-slide>
                        </q-carousel>
                        <q-btn
                          style="background: indigo; color: white"
                          label="Register"
                          align="right"
                        />
                      </div>
                    </div>
                  </q-banner>
                </q-popup-proxy> </q-btn
              >/>
            </q-card-actions>
          </div>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script lang="ts">
import { Vue, Options } from 'vue-class-component';
@Options({
  components: {},
})
export default class SignatureLoginPage extends Vue {
  carousel = {
    slide: 'style',
    lorem:
      'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.',
  };
}
</script>
