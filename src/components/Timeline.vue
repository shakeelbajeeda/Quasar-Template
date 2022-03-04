<template>
  <q-card class="q-mt-sm">
    <div class="q-item q-item-type row no-wrap">
      <div
        class="q-item__section column q-item__section--avatar q-item__section--side justify-center q-pt-md"
      >
        <q-icon name="schedule" color="blue" size="2.5rem" />
      </div>
      <div class="q-item__section column q-item__section--main justify-center">
        <div class="text-h6 q-pt-md">Timeline</div>
      </div>
    </div>
    <div class="q-card__section q-card__section--vert">
      <ul class="q-timeline q-timeline--dense q-timeline--dense--right">
        <li
          class="q-timeline__entry q-timeline__entry--left q-timeline__entry--icon"
        >
          <div class="q-timeline__subtitle"><span></span></div>
          <div class="q-timeline__dot text-red">
            <i
              aria-hidden="true"
              role="presentation"
              class="row items-center justify-center material-icons q-icon notranslate"
              >thumb_up</i
            >
          </div>
          <div class="q-timeline__content">
            <h6 class="q-timeline__title">Pratik Likes your product</h6>
            <div>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </div>
          </div>
        </li>
        <li
          class="q-timeline__entry q-timeline__entry--left q-timeline__entry--icon"
        >
          <div class="q-timeline__subtitle"><span></span></div>
          <div class="q-timeline__dot text-orange">
            <i
              aria-hidden="true"
              role="presentation"
              class="row items-center justify-center material-icons q-icon notranslate"
              >done_all</i
            >
          </div>
          <div class="q-timeline__content">
            <h6 class="q-timeline__title">Product Update</h6>
            <div>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </div>
          </div>
        </li>
        <li
          class="q-timeline__entry q-timeline__entry--left q-timeline__entry--icon"
        >
          <div class="q-timeline__subtitle"><span></span></div>
          <div class="q-timeline__dot text-blue">
            <i
              aria-hidden="true"
              role="presentation"
              class="row items-center justify-center material-icons q-icon notranslate"
              >thumb_up</i
            >
          </div>
          <div class="q-timeline__content">
            <h6 class="q-timeline__title">Jeff Likes your product</h6>
            <div>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </div>
          </div>
        </li>
      </ul>
    </div>
  </q-card>
</template>

<script>
export default {
  props: [""],
};
</script>
