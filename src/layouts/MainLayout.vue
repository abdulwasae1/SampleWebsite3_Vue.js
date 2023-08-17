<template>
  <q-layout>
    <q-header
      style="
        background-image: url(https://thecommercialcoop.com/img/coop-background-img.cb91b6a4.webp);
        background-size: 100%;
        background-repeat: no-repeat;
      "
    >
      <div style="background-color: rgba(0, 0, 0, 0.629)">
        <q-toolbar>
          <q-toolbar-title>
            <div class="row q-mt-lg">
              <div class="col-1 flex justify-end">
                <q-avatar>
                  <img
                    src="../assets/THE_COMMERCIAL_COOP_MARK_2COLOR_1200x.3cf04f2f.webp"
                    style="width: 100%"
                  />
                </q-avatar>
              </div>
              <div class="col-2 q-mt-sm">
                <p class="fontsize-8 text-weight-medium">
                  THE COMMERCIAL CO-OP
                </p>
              </div>
              <div class="col-9 row justify-end">
                <div class="gt-md">
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >home</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >search for sale</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >search for lease</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >search for comps</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >message board</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >contact us</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >about us</q-btn
                  >
                  <q-btn flat style="color: #f1e53e" class="fontsize-6"
                    >sign in</q-btn
                  >
                  <q-btn style="background: red">sign up today</q-btn>
                </div>
                <q-btn
                  flat
                  v-model="rightDrawerOpen"
                  overlay
                  elevated
                  side="right"
                  color="light"
                  icon="menu"
                  class="lt-lg"
                >
                  <q-menu>
                    <q-list style="min-width: 100px">
                      <q-item v-close-popup clickable class="bg-red">
                        <q-item-section class="q-pl-md text-white"
                          >sign up today</q-item-section
                        >
                      </q-item>
                      <q-separator />
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >home</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >search for sale</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >search for lease</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >search for comps</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >message board</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >contact us</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >about us</q-item-section
                        >
                      </q-item>
                      <q-item v-close-popup clickable>
                        <q-item-section class="text-capitalize"
                          >sign in</q-item-section
                        >
                      </q-item>
                    </q-list>
                  </q-menu>
                </q-btn>
              </div>
            </div>
            <div
              style="
                background-image: url(https://thecommercialcoop.com/img/message-board.b205605f.webp);
                background-repeat: no-repeat;
                background-position: center;
                background-size: contain;
              "
            >
              <q-btn
                color="red"
                glossy
                icon-right="send"
                label="view all messages"
                style="margin-left: 15%; margin-top: 35%"
              ></q-btn>
            </div>
          </q-toolbar-title>
        </q-toolbar>
      </div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const rightDrawerOpen = ref(false);

    return {
      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
};
</script>
