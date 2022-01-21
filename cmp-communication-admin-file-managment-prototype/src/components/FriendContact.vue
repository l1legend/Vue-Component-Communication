<template>
  <li>
    <h2>{{ name }} {{ fileIsPublic === '1' ? '(Public)' : '(Private)'}}</h2>
    <button @click="togglePublic">Toggle Public or Private</button>
    <button @click="toggleDetails">{{ detailsAreVisible ? 'Hide' : 'Show' }} Details</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber}}
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
  props: [
    'name',
    'phoneNumber',
    'emailAddress',
    'isPublic',
    'description'
  ],
  data() {
    return {
      detailsAreVisible: false,
      fileIsPublic: this.isPublic
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    togglePublic() {
      if (this.fileIsPublic === '1') {
        this.fileIsPublic = '0';
      }else {
        this.fileIsPublic = '1';
      }
    },
  }
};
</script>