<template>
  <div class="tw-flex tw-items-center tw-cursor-pointer">
    <v-icon class="tw-mr-1 tw-text-green">mdi-calendar-blank</v-icon>
    <span class="tw-text-xl tw-font-medium tw-text-black sm:tw-text-2xl">protector</span>
  </div>
</template>

<script>
import { isPhone } from "@/utils"

export default {
  name: "Logo",

  props: {
    type: {
      type: "timeful" | "betterwhen2meet" | "aprilfools",
      default: "timeful",
    },
  },

  computed: {
    isPhone() {
      return isPhone(this.$vuetify)
    },
    alt() {
      if (this.type === "betterwhen2meet") {
        return "Betterwhen2meet Logo"
      }

      return "Timeful Logo"
    },
    src() {
      switch (this.type) {
        case "timeful":
          return require("@/assets/timeful_logo_with_text.png")
        case "betterwhen2meet":
          return require("@/assets/april_fools_logo.png")
        case "aprilfools":
          return require("@/assets/april_fools_logo.png")
      }
    },
    width() {
      switch (this.type) {
        case "timeful":
          return this.isPhone ? 90 : 110
        case "betterwhen2meet":
          return this.isPhone ? 200 : 300
        case "aprilfools":
          return this.isPhone ? 200 : 300
      }
    },
  },
}
</script>
