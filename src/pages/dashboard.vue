<template>
  <q-page>
    <!-- Top Social Media Box   -->
    <div class="q-mx-sm q-mt-sm">
      <div class="row q-col-gutter-sm">
        <!-- Top Box components start here -->
        <div
          class="col-lg-3 col-md-3 col-sm-12 col-xs-12"
          v-for="box in boxes"
          :key="box"
        >
          <TopBoxVue :box_data="box" />
        </div>
        <!-- Top Box components end here -->

        <!-- Quasar Carousel -->
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
          <CarouselVue :images="carousel_images" />
        </div>
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
          <CarouselVue :images="carousel_images2" />
        </div>
        <!-- Carousel Component end here -->

        <!-- Quasar Cards -->
        <div
          class="col-lg-4 col-md-4 col-sm-12 col-xs-12"
          v-for="card in cards"
          :key="card"
        >
          <CustomCardVue :card="card" />
        </div>

        <!-- Quasar Qtab panel -->
        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 q-mt-md">
          <CustomTab />
        </div>
        <!-- Qimg start here -->

        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 q-mt-md">
          <q-img
            src="https://cdn.pixabay.com/photo/2017/05/10/03/32/lahore-2299773_960_720.jpg"
            height="385px"
          >
            <div class="absolute-bottom text-subtitle1 text-center">
              Minar-e-Pakistan, Lahore
            </div>
          </q-img>
        </div>
        <!-- Quasar checkboxes start here -->
        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12 q-mt-sm">
          <q-card class="bg-primary q-pb-lg">
            <q-toolbar class="text-white q-pt-lg q-pl-lg">
              <q-icon name="library_add_check" size="2rem"></q-icon>
              <q-toolbar-title>To do list</q-toolbar-title>
            </q-toolbar>
            <q-list class="bg-white q-mx-md q-mt-md">
              <Checkboxes
                v-for="checkbox_item in checkbox_items"
                :key="checkbox_item"
                :checkbox_data="checkbox_item"
              />
            </q-list>
          </q-card>
        </div>
        <!-- Quasar Timeline Start here -->
        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
          <TimelineVue />
        </div>
        <!-- Quasar Timeline End here -->
        <!-- Quasar table start here -->
        <div class="col-12">
          <TableComponentVue />
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";
import CustomCardVue from "src/components/CustomCard.vue";
import TopBoxVue from "src/components/TopBox.vue";
import CarouselVue from "src/components/Carousel.vue";
import CustomTab from "src/components/CustomTab.vue";
import Checkboxes from "src/components/Checkboxes.vue";
import TimelineVue from "src/components/Timeline.vue";
import TableComponentVue from "src/components/TableComponent.vue";
export default defineComponent({
  name: "PageIndex",
  components: {
    CustomCardVue,
    TopBoxVue,
    CarouselVue,
    CustomTab,
    Checkboxes,
    TimelineVue,
    TableComponentVue,
  },
  setup() {
    return {
      slide: ref(1),
      tab: ref("mails"),
    };
    `   data: () => ({
      expanded: false,
    });`;
  },
  data() {
    return {
      cards: [
        {
          heading: "Our Quasar Card 1",
          title: "By Shakeel Ahmad",
          content:
            "The QCard component is a great way to display important pieces of grouped content. This pattern is quickly emerging as a core design pattern for Apps, website previews and email content. It assists the viewer by containing and organizing information, while also setting up predictable expectations. With so much content to display at once, and often so little screen real-estate, Cards have fast become the design pattern of choice for many companies, including the likes of Google and Twitter.",
          bg_color: "radial-gradient(circle, #35b0ff 0%, #015a85 100%)",
        },
        {
          heading: "Our Quasar Card 2",
          title: "By Shakeel Ahmad",
          content:
            "The QCard component is a great way to display important pieces of grouped content. This pattern is quickly emerging as a core design pattern for Apps, website previews and email content. It assists the viewer by containing and organizing information, while also setting up predictable expectations. With so much content to display at once, and often so little screen real-estate, Cards have fast become the design pattern of choice for many companies, including the likes of Google and Twitter.",
          bg_color: "radial-gradient(circle, #15a0ff 0%, #034a91 100%)",
        },
        {
          heading: "Our Quasar Card 3",
          title: "By Shakeel Ahmad",
          bg_color: "radial-gradient(circle, #35a2ff 0%, #014a00 100%)",
          content:
            "The QCard component is a great way to display important pieces of grouped content. This pattern is quickly emerging as a core design pattern for Apps, website previews and email content. It assists the viewer by containing and organizing information, while also setting up predictable expectations. With so much content to display at once, and often so little screen real-estate, Cards have fast become the design pattern of choice for many companies, including the likes of Google and Twitter.",
        },
      ],
      boxes: [
        {
          icon_bg: "bg-primary",
          content_bg: "bg-blue-7",
          icon: "perm_identity",
          amount: 200,
          title: "My Account",
        },
        {
          icon_bg: "bg-orange-8",
          content_bg: "bg-orange-6",
          icon: "fab fa-instagram",
          amount: 500,
          title: "Followers",
        },
        {
          icon_bg: "bg-lime-9",
          content_bg: "bg-lime-8",
          icon: "fab fa-google",
          amount: 300,
          title: "Connections",
        },
        {
          icon_bg: "bg-purple-7",
          content_bg: "bg-purple-5",
          icon: "bar_chart",
          amount: 1020,
          title: "Website Visits",
        },
      ],
      carousel_images: [
        "https://cdn.quasar.dev/img/parallax2.jpg",
        "https://cdn.quasar.dev/img/mountains.jpg",
        "https://cdn.quasar.dev/img/parallax1.jpg",
        "https://cdn.quasar.dev/img/quasar.jpg",
      ],
      carousel_images2: [
        "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
        "https://cdn.quasar.dev/img/mountains.jpg",
        "https://cdn.quasar.dev/img/parallax1.jpg",
        "https://cdn.quasar.dev/img/quasar.jpg",
      ],
      checkbox_items: [
        {
          title: "Task Item 1",
          caption: "Task Item 1 Desc",
        },
        {
          title: "Task Item 2",
          caption: "Task Item 2 Desc",
        },
        {
          title: "Task Item 3",
          caption: "Task Item 3 Desc",
        },
        {
          title: "Task Item 4",
          caption: "Task Item 4 Desc",
        },
        {
          title: "Task Item 5",
          caption: "Task Item 5 Desc",
        },
        {
          title: "Task Item 6",
          caption: "Task Item 6 Desc",
        },
        {
          title: "Task Item 7",
          caption: "Task Item 7 Desc",
        },
      ],
    };
  },
});
</script>
