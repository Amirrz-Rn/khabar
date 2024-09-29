<template>
  <div>
    <section>
    <nav class="navbar navbar-light bg-dark">
      <div class="container-fluid">
        
        <a class="navbar-brand">varzesh3</a>
        <form class="d-flex">
          <input
            class="form-control me-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>
    </nav>
    
    <div class="card mt-5" style="width: 18rem;">
      
  <img :src="news.enclosure['@attribute']".url class="card-img-top" alt="...">

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
    <div class="container">
      <footer class="py-3 my-4">
        <ul class="nav justify-content-center border-bottom pb-3 mb-3">
          <li class="nav-item">
            <a href="#" class="nav-link px-2 text-body-secondary">خانه</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link px-2 text-body-secondary"
              >تازه ترین اخبار</a
            >
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link px-2 text-body-secondary">پشتیبانی</a>
          </li>
          <li class="nav-item">
            <a href="#" class="nav-link px-2 text-body-secondary">درباره ما</a>
          </li>
        </ul>
        <p class="text-center text-body-secondary">© 2024 Company, Inc</p>
      </footer>
    </div>
  </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: null,
      loading: true,
      newsList: [],
    };
  },
  mounted() {
    this.getNews();
  },

  methods: {
    getNews() {
      this.axios.get("https://one-api.ir/rss/?token=339075:66f911f72c06a&action=varzesh3")
        .then((Response) => {
          
          this.title = Response.data.result.title
          this.newsList = Response.data.result.item
          console.log(this.newsList);
        })
        .catch((error) => {
          console.log(error.Response);
        });
    },
  },
};
</script>
