<template>
  <li>
    <h2>{{ name }} {{ fileIsPublic === "1" ? "(Public)" : "(Private)" }}</h2>
    <button @click="togglePublic">Toggle Public or Private</button>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? "Hide" : "Show" }} Details
    </button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
      <li>
        <strong>Description</strong>
        {{ description }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  //props: ['name', 'phoneNumber', 'emailAddress', 'isPublic', 'description'],
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true,
    },
    emailAddress: {
      type: String,
      required: true,
    },
    isPublic: {
      type: Boolean,
      required: false,
      default: false,
      validator: function (value) {
        return value === "1" || value === "0";
      },
    },
    description: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      detailsAreVisible: true,
      fileIsPublic: this.isPublic,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    togglePublic() {
      if (this.fileIsPublic === "1") {
        this.fileIsPublic = "0";
      } else {
        this.fileIsPublic = "1";
      }
    },
  },
};
</script>