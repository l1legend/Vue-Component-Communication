<template>
  <section>
    <header>
      <h1>Admin File Management Panel</h1>
    </header>
    <ul>
      <friend-contact
        v-for="file in files"
        :key="file.id"
        :name="file.name"
        :phone-number="file.phone"
        :email-address="file.email"
        :is-favorite="true"
        :description="file.description"  
      ></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      files: [
        {
          id: "1",
          name: "file1",
          phone: "111 111 1111",
          email: "manuel@localhost.com",
          description: "some data"
        },
        {
          id: "2",
          name: "file2",
          phone: "222 222 2222",
          email: "julie@localhost.com",
          description: "some data2"
        },
      ],
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: "Jost", sans-serif;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}
#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
#app button:hover,
#app button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>