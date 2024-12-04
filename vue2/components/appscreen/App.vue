<template>
  <div class="app-grid">
    <swiper :options="swiperOptions" class="swiper-container">
      <swiper-slide v-for="(page, index) in paginatedApps" :key="index">
        <div class="app-page">
          <AppIcon
            v-for="app in page"
            :key="app.title"
            :icon="app.icon"
            :title="app.title"
            :description="app.description"
            :link="app.link"
          />
        </div>
      </swiper-slide>
    </swiper>
    <div class="swiper-pagination"></div>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "vue-awesome-swiper";
import "swiper/css/swiper.css";
import AppIcon from "./components/AppIcon.vue";

export default {
  name: "App",
  components: {
    Swiper,
    SwiperSlide,
    AppIcon,
  },
  data() {
    return {
      swiperOptions: {
        slidesPerView: 1,
        spaceBetween: 10,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        navigation: true,
      },
      apps: [
        { icon: "fas fa-envelope", title: "Messages", description: "Check your messages", link: "https://exampleoflink.com" },
        { icon: "fas fa-calendar-alt", title: "Calendar", description: "View your calendar", link: "https://exampleoflink.com" },
        { icon: "fas fa-map-marker-alt", title: "Maps", description: "Find locations", link: "https://exampleoflink.com" },
        { icon: "fas fa-clock", title: "Clock", description: "View the time", link: "https://exampleoflink.com" },
        { icon: "fas fa-camera", title: "Camera", description: "Take photos", link: "https://exampleoflink.com" },
        { icon: "fas fa-music", title: "Music", description: "Listen to music", link: "https://exampleoflink.com" },
        { icon: "fas fa-video", title: "Videos", description: "Watch videos", link: "https://exampleoflink.com" },
        { icon: "fas fa-book", title: "Books", description: "Read books", link: "https://exampleoflink.com" },
        { icon: "fas fa-gamepad", title: "Games", description: "Play games", link: "https://exampleoflink.com" },
        { icon: "fas fa-shopping-cart", title: "Shop", description: "Buy items", link: "https://exampleoflink.com" },
        { icon: "fas fa-file-alt", title: "Docs", description: "View documents", link: "https://exampleoflink.com" },
        { icon: "fas fa-calculator", title: "Calculator", description: "Perform calculations", link: "https://exampleoflink.com" },
        { icon: "fas fa-bell", title: "Notifications", description: "View notifications", link: "https://exampleoflink.com" },
        { icon: "fas fa-paint-brush", title: "Art", description: "Create art", link: "https://exampleoflink.com" },
        { icon: "fas fa-heart", title: "Health", description: "Track health", link: "https://exampleoflink.com" },
        { icon: "fas fa-car", title: "Ride", description: "Book a ride", link: "https://exampleoflink.com"},
        { icon: "fas fa-hotel", title: "Hotels", description: "Book hotels", link: "https://exampleoflink.com"},
        { icon: "fas fa-train", title: "Trains", description: "Book train tickets", link: "https://exampleoflink.com"},
        { icon: "fas fa-plane", title: "Flights", description: "Book flights", link: "https://exampleoflink.com" },
        { icon: "fas fa-utensils", title: "Food", description: "Order food", link: "https://exampleoflink.com"},
        { icon: "fas fa-tv", title: "TV", description: "Watch TV", link: "https://exampleoflink.com"},
        { icon: "fas fa-laptop", title: "Work", description: "Work from home", link: "https://exampleoflink.com" },
        { icon: "fas fa-cloud", title: "Cloud", description: "Cloud storage", link: "https://exampleoflink.com" },
        { icon: "fas fa-code", title: "Code", description: "Write code", link: "https://exampleoflink.com"},
        { icon: "fas fa-camera-retro", title: "Photos", description: "View photos", link: "https://exampleoflink.com" },
        { icon: "fas fa-chart-line", title: "Finance", description: "Track finances", link: "https://exampleoflink.com" },
        { icon: "fas fa-thermometer-half", title: "Weather", description: "Check weather", link: "https://exampleoflink.com" },
        { icon: "fas fa-shopping-bag", title: "Deals", description: "Find deals", link: "https://exampleoflink.com" },
        { icon: "fas fa-users", title: "Social", description: "Social media", link: "https://exampleoflink.com" },
        { icon: "fas fa-headphones", title: "Podcasts", description: "Listen to podcasts", link: "https://exampleoflink.com" },
        { icon: "fas fa-film", title: "Cinema", description: "Watch movies", link: "https://exampleoflink.com" },
        { icon: "fas fa-newspaper", title: "News", description: "Read news", link: "https://exampleoflink.com" },
        { icon: "fas fa-running", title: "Fitness", description: "Track fitness", link: "https://exampleoflink.com"},
        { icon: "fas fa-hiking", title: "Travel", description: "Explore places", link: "https://exampleoflink.com" },
        { icon: "fas fa-puzzle-piece", title: "Puzzle", description: "Solve puzzles", link: "https://exampleoflink.com" },
        { icon: "fas fa-comment-dots", title: "Chat", description: "Chat with friends", link: "https://exampleoflink.com" },
        { icon: "fas fa-address-book", title: "Contacts", description: "View contacts", link: "https://exampleoflink.com" },
        { icon: "fas fa-wifi", title: "WiFi", description: "Connect to WiFi", link: "https://exampleoflink.com" },
        { icon: "fas fa-home", title: "Home", description: "Smart home control", link: "https://exampleoflink.com" },
        { icon: "fas fa-credit-card", title: "Payments", description: "Make payments", link: "https://exampleoflink.com" },
        { icon: "fas fa-link", title: "Links", description: "Manage links", link: "https://exampleoflink.com" },
        { icon: "fas fa-shield-alt", title: "Security", description: "Enhance security", link: "https://exampleoflink.com" },
        { icon: "fas fa-clipboard", title: "Clipboard", description: "Copy items", link: "https://exampleoflink.com" },
        { icon: "fas fa-life-ring", title: "Help", description: "Get help", link: "https://exampleoflink.com" },
        { icon: "fas fa-book-reader", title: "Learning", description: "Online courses", link: "https://exampleoflink.com" },
        { icon: "fas fa-edit", title: "Notes", description: "Write notes", link: "https://exampleoflink.com" },
        { icon: "fas fa-smile", title: "Emoji", description: "Emoji stickers", link: "https://exampleoflink.com"},
      ],
    };
  },
  computed: {
    paginatedApps() {
      const chunkSize = 20;
      return this.apps.reduce((result, value, index) => {
        const chunkIndex = Math.floor(index / chunkSize);
        if (!result[chunkIndex]) result[chunkIndex] = [];
        result[chunkIndex].push(value);
        return result;
      }, []);
    },
  },
};
</script>

<style lang="less">
.app-grid {
  width: 100%;
  height: 100vh;
  background-color: #000;
  color: #ffcc00;
  overflow: hidden;

  .swiper-container {
    height: 100%;
  }

  .swiper-pagination {
    bottom: 10px;
  }

  .app-page {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(5, 1fr);
    gap: 15px;
    padding: 20px;
  }
}
</style>
