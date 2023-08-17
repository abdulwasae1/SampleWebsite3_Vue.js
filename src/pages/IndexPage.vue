<template>
  <q-page>
    <div class="bg-grey-2">
      <div style="width: 42%; margin-left: 30%" class="q-pt-xl q-pb-xl">
        <p class="fontsize-18 text-weight-medium">
          THE ONLY ALL IN ONE PLATFORM THAT CUTS BROKER TECH COSTS BY
          <span class="text-red">UP TO 70%</span>
        </p>
        <q-btn color="red" glossy class="fontsize-10 q-ml-xl q-mt-lg"
          >create a free account and start posting today</q-btn
        >
        <p class="fontsize-7 q-mt-xl text-grey text-weight-medium">
          Start Searching The Co-Opportunity Message Board!
        </p>
        <q-btn color="amber-8 shadow-4" class="fontsize-8"
          >search by location</q-btn
        >
        <div padding class="bg-grey-5 q-pa-md">
          <div class="row">
            <div class="col-md-10">
              <q-input
                filled
                style="width: 94%"
                class="bg-white"
                v-model="ph"
                placeholder="Location e.g. Denver, co"
                :dense="dense"
              />
            </div>
            <div class="col-md-2">
              <q-btn
                class="fontsize-8 q-mt-xs"
                style="margin-left: 5%"
                color="red"
                >search</q-btn
              >
            </div>
          </div>
        </div>
      </div>
    </div>

    <div>
      <p
        class="fontsize-18 q-mt-xl text-weight-bolder"
        style="text-align: center"
      >
        Stay Up To Date With <br />
        The Co-Opportunity Message Board
      </p>

      <div
        class="row"
        style="
          background-image: url(data:image/webp;base64,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);
          background-repeat: no-repeat;
          background-position: bottom;
        "
      >
        <div class="col-6">
          <p
            class="fontsize-17 text-orange text-weight-medium"
            style="margin-top: 12%; margin-left: 15%"
          >
            FREE UP YOUR INBOX & COMMUNICATE WITH EFFICIENCY
          </p>
          <div class="row">
            <div class="col-3 flex justify-end q-pr-md">
              <q-img
                src="../assets/tick.png"
                style="width: 15%; height: 30%"
              ></q-img>
            </div>
            <div class="col-9">
              <p class="fontsize-8">
                Location Specific Posting of Haves, Wants, Needs, Announcements,
                Off Market Deals, Job Postings and Real Estate News.
              </p>
            </div>
          </div>
          <div class="row">
            <div class="col-3 flex justify-end q-pr-md">
              <q-img
                src="../assets/tick.png"
                style="width: 15%; height: 30%"
              ></q-img>
            </div>
            <div class="col-9">
              <p class="fontsize-8">
                Public View Message Board with Broker Only Posting and Direct
                <br />
                Messaging.
              </p>
            </div>
          </div>
          <div class="row">
            <div class="col-3 flex justify-end q-pr-md">
              <q-img
                src="../assets/tick2.png"
                style="width: 12%; height: 60%"
              ></q-img>
            </div>
            <div class="col-9">
              <p class="fontsize-8">
                Upload Listings on your
                <span class="text-red-9 text-weight-bold">Free Account</span>
                and Attach to Posts in Real Time.
              </p>
            </div>
          </div>
          <div class="row">
            <div class="col-3 flex justify-end q-pr-md">
              <q-img
                src="../assets/tick2.png"
                style="width: 12%; height: 60%"
              ></q-img>
            </div>
            <div class="col-9">
              <p class="fontsize-8">
                Start your 90 Day
                <span class="text-red-9 text-weight-bold"
                  >Free Trial Today,</span
                >
                then enjoy unlimited posting for only
                <span class="text-red-9 text-weight-bold">$19/ month!</span>
              </p>
            </div>
          </div>
        </div>
        <div class="col-6">
          <q-img src="../assets/the-coopportunity-board.9e362907.webp"></q-img>
        </div>
      </div>
    </div>

    <div
      style="
        background-image: url(https://thecommercialcoop.com/img/coop-background-img.cb91b6a4.webp);
        background-size: 100%;
      "
    >
      <div style="background-color: rgba(0, 0, 0, 0.801); text-align: center">
        <p
          class="fontsize-18 text-red-7 text-weight-medium q-pt-xl"
          style="width: 70%; margin-left: 15%"
        >
          FINALLY, AN ALL IN ONE PLATFORM FOR COMMERCIAL SEARCHING, MARKETING
          AND COMMUNICATING FOR A FRACTION OF THE PRICE BROKERS PAY FOR MULTIPLE
          SUBSCRIPTIONS.
        </p>
        <div class="row q-mt-xl">
          <div class="col-md-6 col-12 flex justify-end">
            <q-img src="../assets/pc.webp" style="width: 90%"></q-img>
          </div>
          <div class="col-6" style="text-align: start">
            <p class="fontsize-18 q-mt-xl text-weight-medium text-amber-9">
              MARKETING MADE EASY
            </p>
            <li class="fontsize-8 text-white q-pt-lg">
              Always FREE For Brokers To Upload Unlimited Listings To The Public
              Site.
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              Branded Brochure Generator With Imbedded Financial Calculator.
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              CMA Generator and Comps Platform
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              Social Media Inspired Message Board To Post Clients Needs And
              Announcements
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              Share Listings with one click
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              Email listing links from your personal email accounts and contacts
            </li>
            <li class="fontsize-8 text-white q-pt-lg">
              Dynamic Dashboard With Live Search Updates
            </li>
          </div>
        </div>
      </div>
    </div>

    <div
      style="
        background-image: url(data:image/webp;base64,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);
        text-align: center;
        background-repeat: no-repeat;
        background-position: bottom;
      "
    >
      <p class="fontsize-18 text-weight-medium q-pt-xl">
        <span class="text-red-8">FREE SEARCHING</span> ON THE PUBLIC SITE
      </p>
      <div class="row justify-center">
        <div class="col-6" style="text-align: start">
          <p class="fontsize-10 text-weight-medium">
            Start Searching Denver and Mesa County Now!
          </p>
          <q-btn-group push>
            <q-btn
              color="white"
              glossy
              text-color="black"
              push
              label="search for sale"
              class="fontsize-8"
            />
            <q-btn
              color="white"
              glossy
              text-color="black"
              push
              label="search for lease"
              class="fontsize-8"
            />
            <q-btn
              color="white"
              glossy
              text-color="black"
              push
              label="search for comps"
              class="fontsize-8"
            />
          </q-btn-group>
          <div padding class="bg-grey-5 q-pa-md">
            <div class="row">
              <div class="col-md-3 col-12">
                <q-btn-dropdown
                  flat
                  color="white"
                  class="q-pa-md text-grey bg-grey-3 text-capitalize q-mt-xs fontsize-6 text-weight-regular"
                  label="select property type"
                >
                  <q-list>
                    <q-item clickable v-close-popup @click="onItemClick">
                      <q-item-section>
                        <q-item-label>Photos</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable v-close-popup @click="onItemClick">
                      <q-item-section>
                        <q-item-label>Videos</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable v-close-popup @click="onItemClick">
                      <q-item-section>
                        <q-item-label>Articles</q-item-label>
                      </q-item-section>
                    </q-item>
                  </q-list>
                </q-btn-dropdown>
              </div>
              <div class="col-lg-7 col-12">
                <q-input
                  filled
                  style="width: 96%"
                  class="bg-white q-mt-xs"
                  v-model="ph"
                  placeholder="Location"
                  :dense="dense"
                />
              </div>
              <div class="col-md-2 col-12">
                <q-btn
                  class="fontsize-8 q-mt-xs"
                  style="margin-left: 6%"
                  color="red-8"
                  >search</q-btn
                >
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="row">
        <div class="col-md-6" style="text-align: start">
          <p
            class="fontsize-15 text-weight-medium"
            style="margin-left: 20%; margin-top: 10%"
          >
            THE ONLY COMMERCIAL REAL ESTATE TOOL
            <span class="text-red-8">YOU'LL EVER NEED</span>
          </p>
          <p
            style="margin-left: 20%"
            class="fontsize-15 text-amber-7 text-weight-medium"
          >
            SEARCH LISTINGS & COMPS:
          </p>

          <div style="margin-left: 25%">
            <li class="fontsize-9 q-pt-md">
              We're just starting out, so join Colorado Brokers in adding your
              listings for free - Nationwide - with no limits or per listing
              charges!
            </li>
            <li class="fontsize-9 q-pt-md">
              Now Searching Denver and Mesa Counties, the rest is up to YOU.
            </li>
            <li class="fontsize-9 q-pt-md">
              CMA Generator with Colorado Comps Database growing by the day.
            </li>
          </div>
          <div style="text-align: center">
            <q-btn
              color="red"
              glossy
              icon-right="send"
              label="search for sale"
              class="q-mt-xl fontsize-9"
            ></q-btn>
          </div>
        </div>
        <div class="col-md-6 col-12">
          <q-img src="../assets/maps.webp"></q-img>
        </div>
      </div>
    </div>

    <div
      style="
        background-image: url(https://thecommercialcoop.com/img/coop-background-img.cb91b6a4.webp);
        background-size: 100%;
        background-repeat: no-repeat;
      "
    >
      <div
        style="background-color: rgba(0, 0, 0, 0.772); text-align: center"
        class="row justify-center"
      >
        <div class="col-8">
          <p class="fontsize-18 text-white text-weight-medium q-pt-xl q-pb-xl">
            SPECIAL RATES FOR EARLY SUBSCRIBERS WITH EXTENDED TRIAL PERIODS
            LEADING TO OUR 2023 PRICING SCHEDULE
          </p>
          <q-btn color="red" glossy class="fontsize-11 q-mb-xl"
            >start your 90 day free trial of the full platform today</q-btn
          >
        </div>
      </div>
    </div>

    <div style="text-align: center">
      <p class="fontsize-15 q-pt-lg text-red-9 text-weight-medium">
        THE COMMERCIAL CO-OP FEATURED LISTINGS
      </p>
      <div class="row justify-evenly">
        <div class="col-5">
          <div class="row justify-evenly">
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
          </div>
        </div>
        <div class="col-5">
          <div class="row justify-evenly">
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
          </div>
        </div>
      </div>
      <div class="row justify-evenly q-mt-lg">
        <div class="col-5">
          <div class="row justify-evenly">
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
          </div>
        </div>
        <div class="col-5">
          <div class="row justify-evenly">
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
            <div class="col-5">
              <q-card class="my-card" flat bordered>
                <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg" />

                <q-card-section>
                  <q-btn
                    fab
                    color="primary"
                    icon="place"
                    class="absolute"
                    style="top: 0; right: 12px; transform: translateY(-50%)"
                  />

                  <div class="row no-wrap items-center">
                    <div class="col text-h6 ellipsis">Cafe Basilico</div>
                    <div
                      class="col-auto text-grey text-caption q-pt-md row no-wrap items-center"
                    >
                      <q-icon name="place" />
                      250 ft
                    </div>
                  </div>

                  <q-rating v-model="stars" :max="5" size="32px" />
                </q-card-section>

                <q-card-section class="q-pt-none">
                  <div class="text-subtitle1">$・Italian, Cafe</div>
                  <div class="text-caption text-grey">
                    Small plates, salads & sandwiches in an intimate setting.
                  </div>
                </q-card-section>

                <q-separator />

                <q-card-actions>
                  <q-btn flat round icon="event" />
                  <q-btn flat color="primary"> Reserve </q-btn>
                </q-card-actions>
              </q-card>
            </div>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>
