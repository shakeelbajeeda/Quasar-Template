<template>
  <q-page>
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
        <!-- Latest Sale table start here -->
        <div class="col-12">
          <TableData/>
        </div>
        <!-- QTab start here -->
        <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
          <CustomTab/>
        </div>
           <div class="col-lg-6 col-md-6 col-sm-12 col-xs-12">
          <Carousel :images="carousel_images" />
        </div>
      </div>
    </div>
  </q-page>
</template>
<script>
import { defineComponent, ref } from "vue";
import TopBoxVue from "src/components/TopBox.vue";
import TableData from "src/components/TableData.vue";
import CustomTab from "src/components/CustomTab.vue";
import Carousel from "src/components/Carousel.vue";
export default defineComponent({
  components: {
    TopBoxVue,
    TableData,
    CustomTab,
    Carousel
},
  data() {
    return {
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
        "https://images.unsplash.com/photo-1622546758596-f1f06ba11f58?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=921&q=80",
        "https://images.unsplash.com/photo-1628755615663-d14c78ed24f0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=876&q=80",
        "https://thumbs.dreamstime.com/z/lahore-fort-11603114.jpg",
        "https://pbs.twimg.com/media/BrtvN2kCcAAsHmo?format=jpg&name=small",
      ],
    };
  },
});
</script>
