<template>
  <div id="app">
    <div class="container my-5">
      <div class="row">
        <div :key="index" v-for="(a, index) in view_articels" class="card bg-primary text-white my-1 border-white shadow-sm  col-md-4">
          <div class="card-body">
            <h2 class="card-title text-center font-weight-bolder">{{ a.id }}</h2>
          </div>
        </div>
      </div>

      <nav aria-label="Page navigation example ">
        <ul class="pagination justify-content-center my-3">
          <li class="page-item" :class="{'disabled': current_page == 0}">
            <a class="page-link" href="#" @click="go_back()" >Previous</a>
          </li>
          <li class="page-item" :key="index" v-for="(links, index) in page_counter" :class="{'active': current_page == index}">
            <a class="page-link" href="#" @click="go_to(index)">{{ links }}</a>
          </li>
          <li class="page-item" :class="{'disabled': current_page == page_counter - 1}">
            <a class="page-link" href="#" @click="go_forward()">Next</a>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      current_page: 0,
      articlePerPage: 6,
      all_articles: [
        {
          id: 1
        },
        {
          id: 2
        },
        {
          id: 3
        },
        {
          id: 4
        },
        {
          id: 5
        },
        {
          id: 6
        },
        {
          id: 7
        },
        {
          id: 8
        },
        {
          id: 9
        },
        {
          id: 10
        },
        {
          id: 11
        },
        {
          id: 12
        },
        {
          id: 13
        },
        {
          id: 14
        },
        {
          id: 15
        },
        {
          id: 16
        },
        {
          id: 17
        },
        {
          id: 18
        },
        {
          id: 19
        },
        {
          id: 20
        },
        {
          id: 21
        },
        {
          id: 22
        },
        {
          id: 23
        },
        {
          id: 24
        },
        {
          id: 25
        },
        {
          id: 26
        },
        {
          id: 27
        },
        {
          id: 28
        },
        {
          id: 29
        },
        {
          id: 30
        },
        {
          id: 31
        },
        {
          id: 32
        },
        {
          id: 33
        },
        {
          id: 34
        },
        {
          id: 35
        },
        {
          id: 36
        },
        {
          id: 37
        },
        {
          id: 38
        },
        {
          id: 39
        },
        {
          id: 40
        },
        {
          id: 41
        },
        {
          id: 42
        },
        {
          id: 43
        },
        {
          id: 44
        },
        {
          id: 45
        },
        {
          id: 46
        },
        {
          id: 47
        },
        {
          id: 48
        },
        {
          id: 49
        },
        {
          id: 50
        },
        {
          id: 51
        }
      ]
    };
  },
  methods:{
    go_forward(){
      this.current_page += 1
    },
    go_to(index){
      this.current_page = index
    },
    go_back(){
      this.current_page -= 1
    },
  },
  computed: {
    page_counter() {
      return Math.floor( this.all_articles.length / this.articlePerPage )
    },
    view_articels(){
      let last_article = this.current_page * this.articlePerPage;

      return this.all_articles.slice(last_article, last_article + this.articlePerPage)
    },
  }
};
</script>
