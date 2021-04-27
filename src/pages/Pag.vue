<template>
  <q-page>
    <div class="row">
      <q-table
        title="Treats"
        :data="posts"
        :columns="columns"
        row-key="name"
        class="col"
      />
    </div>
  </q-page>
</template>

<script>
export default {
  name: "Page",
  data() {
    return {
      columns: [
        {
          name: "title",
          id: "id",
          label: "Id post"
        }
      ],
      posts: []
    };
  },
  methods: {
    getPosts() {
      this.$api
        .get(
          "https://jsonplaceholder.typicode.com"
        )
        .then(res => {
         this.posts = res.data
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>
