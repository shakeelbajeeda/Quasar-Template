<template>
  <q-card>
    <q-tabs
      v-model="tab"
      dense
      class="text-grey"
      :class="$q.screen.lt.sm ? 'q_tab_size' : 'q_tab_size_md'"
      active-color="primary"
      indicator-color="primary"
      align="justify"
      narrow-indicator
    >
      <q-tab
        v-for="item in tabs"
        :key="item"
        :name="item.name"
        :icon="item.icon"
      >
        {{ item.title }}
        <q-badge color="red" floating>{{ item.badge_count }}</q-badge>
      </q-tab>
    </q-tabs>

    <q-separator />

    <q-tab-panels v-model="tab" animated>
      <q-tab-panel name="contact">
        <q-list>
          <ContactVue
            v-for="contact in Contacts"
            :key="contact"
            :contact_data="contact"
          />
        </q-list>
      </q-tab-panel>

      <q-tab-panel name="message">
        <q-list>
          <MessageVue
            v-for="message in Messages"
            :key="message"
            :message_data="message"
          />
        </q-list>
      </q-tab-panel>

      <q-tab-panel name="notification">
        <q-list>
          <NotificationVue
            v-for="notification in Notifications"
            :key="notification"
            :notification_data="notification"
          />
        </q-list>
      </q-tab-panel>
    </q-tab-panels>
  </q-card>
</template>

<script>
import NotificationVue from "src/components/Notification.vue";
import ContactVue from "src/components/Contact.vue";
import MessageVue from "src/components/Message.vue";
export default {
  props: [""],
  components: { NotificationVue, ContactVue, MessageVue },
  data() {
    return {
      tab: "contact",
      tabs: [
        {
          name: "contact",
          icon: "contacts",
          title: "Contact",
          badge_count: "6",
        },
        {
          name: "message",
          icon: "message",
          title: "Massage",
          badge_count: "4",
        },
        {
          name: "notification",
          icon: "notifications",
          title: "Notification",
          badge_count: "5",
        },
      ],
      Notifications: [
        {
          icon: "remove_circle",
          color: "teal",
          text_color: "white",
          content: "you can remove this content",
        },
        {
          icon: "error_outline",
          color: "red-10",
          text_color: "white",
          content: "Hard Disk error",
        },
        {
          icon: "report",
          color: "red-10",
          text_color: "white",
          content: "Are you sure report this error",
        },
        {
          icon: "wifi_off",
          color: "teal",
          text_color: "white",
          content: "Wifi Connection Field",
        },
        {
          icon: "missed_video_call",
          color: "amber-10",
          text_color: "white",
          content: "Missed Video Calls",
        },
      ],
      Contacts: [
        {
          src: "https://pbs.twimg.com/profile_images/1433468735331962881/Xtjqc9eg_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Shakeel Ahmad",
          contact_profession: "Developer",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1386618778318950400/nrIMoNnr_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Sardar Tanveer",
          contact_profession: "Designer",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1350679365395341312/2NgqsUxI_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Abdul Waheed",
          contact_profession: "Software Engineer",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1446360024289325063/zl9BZTx-_400x400.png",
          color: "amber-10",
          text_color: "white",
          contact_name: "Akhlaq Ahmed",
          contact_profession: "Web Developer",
        },
        {
          src: "https://scontent.flhe4-1.fna.fbcdn.net/v/t1.6435-9/127001018_104683438144553_3653274587018320671_n.png?_nc_cat=100&ccb=1-5&_nc_sid=09cbfe&_nc_ohc=MuKyo0xPY8QAX-bhdTK&_nc_ht=scontent.flhe4-1.fna&oh=00_AT_SOt0c5vuQo8RqpGO9NAySz_PyixqaUK1KJbLnMEZCOg&oe=6242E9B1",
          color: "amber-10",
          text_color: "white",
          contact_name: "NodeSol",
          contact_profession: "Software House",
        },
      ],
      Messages: [
        {
          src: "https://pbs.twimg.com/profile_images/1433468735331962881/Xtjqc9eg_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Shakeel Ahmad",
          contact_message:
            "Developer I'll be in your neighborhood doing errands this weeer",
          message_time: "Just now",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1350679365395341312/2NgqsUxI_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Abdul Waheed",
          contact_message:
            "I'll send your payment in your account after 2 Hours",
          message_time: "01:11 AM",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1446360024289325063/zl9BZTx-_400x400.png",
          color: "amber-10",
          text_color: "white",
          contact_name: "Akhlaq Ahmed",
          contact_message:
            "You can use a Snackbar to display a brief message to the user. ",
          message_time: "59 mins ago",
        },
        {
          src: "https://pbs.twimg.com/profile_images/1386618778318950400/nrIMoNnr_400x400.jpg",
          color: "amber-10",
          text_color: "white",
          contact_name: "Sardar Tanveer",
          contact_message: "Can i call you ???",
          message_time: "2 hours ago",
        },
        {
          src: "https://scontent.flhe4-1.fna.fbcdn.net/v/t1.6435-9/127001018_104683438144553_3653274587018320671_n.png?_nc_cat=100&ccb=1-5&_nc_sid=09cbfe&_nc_ohc=MuKyo0xPY8QAX-bhdTK&_nc_ht=scontent.flhe4-1.fna&oh=00_AT_SOt0c5vuQo8RqpGO9NAySz_PyixqaUK1KJbLnMEZCOg&oe=6242E9B1",
          color: "amber-10",
          text_color: "white",
          contact_name: "NodeSol",
          contact_message: "Software House",
          message_time: "5 hours ago",
        },
      ],
    };
  },
};
</script>
