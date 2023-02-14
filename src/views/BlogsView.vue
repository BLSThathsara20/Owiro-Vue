<template>
  <div class="blogs">
    <section class="blog">
      <div class="container">
        <div class="row row-cols-1 row-cols-md-1 g-4 pb-5">
          <div class="col" v-for="(blog, index) in paginatedBlogs" :key="index">
            <div class="card">
              <img :src="blog.image" class="card-img-top" alt="...">
              <div class="card-body">
                <h5 class="card-title">{{ blog.title }}</h5>
                <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
              </div>
            </div>
          </div>
        </div>
        <nav aria-label="Page navigation example">
          <ul class="pagination justify-content-center">
            <li class="page-item" :class="{ disabled: currentPage === 1 }">
              <a class="page-link" href="#" aria-label="Previous" @click="previousPage()">
                <span aria-hidden="true">&laquo;</span>
              </a>
            </li>
            <li class="page-item" v-for="page in pages" :key="page" :class="{ active: currentPage === page }">
              <a class="page-link" href="#" @click="changePage(page)">{{ page }}</a>
            </li>
            <li class="page-item" :class="{ disabled: currentPage === totalPages }">
              <a class="page-link" href="#" aria-label="Next" @click="nextPage()">
                <span aria-hidden="true">&raquo;</span>
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Blogs',
  components: {},
  data() {
    return {
      blogs: [
        {
          title: 'Blog 01',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 02',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 03',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 04',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 05',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 06',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 07',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
        {
          title: 'Blog 08',
          image: require('@/assets/image/blogs/bl-gallery-img6.jpg'),
        },
      ],
      itemsPerPage: 3,
      currentPage: 1,
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.blogs.length / this.itemsPerPage);
    },
    pages() {
      let pagesArray = [];
      for (let i = 1; i <= this.totalPages; i++) {
        pagesArray.push(i);
      }
      return pagesArray;
    },
    paginatedBlogs() {
      const startIndex = (this.currentPage - 1) * this.itemsPerPage;
      const endIndex = startIndex + this.itemsPerPage;
      return this.blogs.slice(startIndex, endIndex);
    },
  },
  methods: {
    changePage(page) {
      this.currentPage = page;
    },
    previousPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
      }
    },
  },
};
</script>


<style lang="scss" scoped>
//Variables
$color-1: #000;

$font-1 : 'Syne', sans-serif;
$font-2 : 'Heebo', sans-serif;

.blogs{
  .blog{
    padding-top: 80px;
    padding-bottom: 120px;
  }
}

</style>