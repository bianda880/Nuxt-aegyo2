<template>
  <div>
    <!-- jumbotron -->
    <section class="jumbotron">
      <div class="container-fluid">
        <div class="row">
          <div class="col-sm-6">
            <a href="">
              <div class="card bg-dark text-white">
                <img
                  :src="articles.data[0].image_path"
                  class="card-img"
                  alt="..."
                />
                <div class="card-img-overlay mx-auto">
                  <p class="card-title categori">
                    {{
                      articles.data[0].category &&
                      articles.data[0].category.name
                    }}
                  </p>
                </div>
                <div class="sm card-footer">
                  <h6 class="card-text">{{ articles.data[0].title }}</h6>
                  <p class="card-text">
                    By
                    {{
                      articles.data[0].created_by &&
                      articles.data[0].created_by.name
                    }}
                    {{
                      $moment(articles.data[0].publish_date).format("MMM Do YY")
                    }}
                  </p>
                </div>
              </div>
            </a>
            <br />
          </div>
          <div class="col-sm-6">
            <div class="row row-cols-2" v-if="articles.data.length">
              <div
                class="col"
                v-for="article in articles.data.slice(1, 5)"
                :key="article.id"
              >
                <a href="">
                  <div class="card bg-dark text-white">
                    <img
                      :src="article.image_path"
                      class="card-img img-jum"
                      alt="..."
                    />
                    <div class="card-img-overlay mx-auto">
                      <p class="card-title categori">
                        {{ article.category && article.category.name }}
                      </p>
                    </div>
                    <div class="sm card-footer">
                      <h6 class="card-text">{{ article.title }}</h6>
                      <p class="card-text">
                        By
                        {{ article.created_by && article.created_by.name }}
                        {{ $moment(article.publish_date).format("MMM Do YY") }}
                      </p>
                    </div>
                  </div>
                </a>
                <br />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <br />
    <!-- end jumbotron -->
    <div class="container">
      <div class="row">
        <div class="col-sm-8">
          <div
            class="artikel"
            v-for="article in articles.data"
            :key="article.id"
          >
            <div class="row">
              <div class="col-sm-3">
                <a href="">
                  <div class="card bg-dark text-white">
                    <img :src="article.image_path" class="card-img" alt="..." />
                    <div class="card-img-overlay mx-auto">
                      <p class="card-title categori">
                        {{ article.category && article.category.name }}
                      </p>
                    </div>
                  </div>
                </a>
              </div>
              <div class="col-sm-9">
                <h6>{{ article.title }}</h6>
                <p class="desc">
                  {{ article.description }}
                </p>
                <p class="card-text">
                  By {{ article.created_by && article.created_by.name }}
                  {{ $moment(article.publish_date).format("MMM Do YY") }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  async asyncData() {
    const { data } = await axios.get(
      "https://app-staging.semesta.io/api/5b460ed754feef0f654bc58a31ce2de7/categories/all/articles"
    );
    return { articles: data };
  },
};
</script>
