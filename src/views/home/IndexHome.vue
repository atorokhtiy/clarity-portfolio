<template>
  <div id="IndexHome" class="body--wrapper">
    <!-- BANNER TOP -->
    <section class="banner-top">
      <div class="banner-top__image-background">
        <div class="img">
          <img src="http://www.primewalls.com/images/magnetic-banner.jpg" alt="Corporate IT Profesional">
          <div class="banner-description">
            <div class="box-desc">
              <div class="title">
                І – АР – СІ
              </div>
              <div class="description">
                Best way to order devices.
              </div>
              <router-link :to="'about-us'" class="btn btn-lg btn-default">
                About Us
              </router-link>
              <router-link :to="'portofolios'" class="btn btn-lg btn-danger">
                Portofolio
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="intermezo-banner-top">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="pull-left">
              <div class="title">
                Look how we work
              </div>
            </div>
            <div class="pull-right">
              <router-link :to="'portofolios'" class="btn btn-lg btn-warning">
                <i class="fa fa-eye"></i>
                Request Full PORTOFOLIO
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- /.BANNER TOP -->
    <!-- OUR SERVICE -->
    <section class="section--wrapper service-wrapper">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="title--top">
              <div class="title">
                Our Services
              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <div class="service-wrapper__list-service">
              <ul>
                <li>
                  <div class="list-service__box-icon">
                    <img src="static/images/gallery/service/company-profile.png" alt="">
                  </div>
                  <div class="list-service__title">
                    Best Deals
                  </div>
                </li>
                <li>
                  <div class="list-service__box-icon">
                    <img src="static/images/gallery/service/online-shop.png" alt="">
                  </div>
                  <div class="list-service__title">
                    E-Commerce
                  </div>
                </li>
                <li>
                  <div class="list-service__box-icon">
                    <img src="static/images/gallery/service/sistem-informasi.png" alt="">
                  </div>
                  <div class="list-service__title">
                    Automated Bills
                  </div>
                </li>
                <li>
                  <div class="list-service__box-icon">
                    <img src="static/images/gallery/service/world-map.png" alt="">
                  </div>
                  <div class="list-service__title">
                    Worldwide
                  </div>
                </li>
                <li>
                  <div class="list-service__box-icon">
                    <img src="static/images/gallery/service/startup.png" alt="">
                  </div>
                  <div class="list-service__title">
                    Speed
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- /.OUR SERVICE -->
    <!-- POINT-POINT -->
    <section class="point-wrapper">
      <div class="container">
        <div class="row">
          <div class="col-md-8">
            <div class="row">
              <div class="col-md-12">
                <div class="point-wrapper__box-title-top">
                  <div class="title">
                    Latest Technologies
                  </div>
                  <div class="description">
                    Best service! Best clients!
                  </div>
                </div>
              </div>
              <div class="col-md-6">
                <div class="point-wrapper__box-point">
                  <div class="image">
                    <!-- <img :src="tech.img" alt=""> -->
                    <img src="" alt="">
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-4">
            <div class="row">
              <div class="col-md-12">
                <div class="point-wrapper__box-counting">
                  <div class="box-head">
                    <div class="count-big">
                      50
                    </div>
                    <div class="count-desc">
                      total client
                    </div>
                  </div>
                  <hr>
                  <div class="box-body">
                    <p>
                      <span>30</span>&nbsp;company</p>
                    <p>
                      <span>10</span>&nbsp;online store</p>
                    <p>
                      <span>05</span>&nbsp;goverment</p>
                    <p>
                      <span>05</span>&nbsp;personal</p>
                  </div>
                </div>
                <br>
                <router-link :to="'portofolios'" class="btn btn-block btn-lg btn-warning">
                  <i class="fa fa-eye"></i>
                  Request Full PORTOFOLIO
                </router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- /.POINT-POINT -->
    <!-- LATEST-PROJECT -->
    <section class="section--wrapper">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="title--top">
              <div class="title">
                latest projects
              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-3" v-for="project in lates_project" v-bind:key="project.id">
            <div class="list-portofolio">
              <div class="list-portofolio__image">
                <img :src="project.client_logo_url">
                <div class="box-description">
                  <router-link :to="'portofolios/detail/3'" class="title">
                    {{ project.title }}
                  </router-link>
                  <div class="type">
                    {{ project.client_name }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <div class="text-center">
              <br>
              <br>
              <router-link :to="'portofolios'" class="btn btn-lg btn-danger">
                <i class="fa fa-eye"></i>
                Request Full PORTFOLIO
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- /.LATEST-PROJECT -->
  </div>
</template>

<script>
export default {
  name: 'IndexHome',
  data () {
    return {
      about_us: [],
      lates_project: []
    }
  },
  created () {
    let options = {
      headers: {
        'Content-Type': 'multipart/form-data',
        'Api-Key': ''
      }
    }

    let body = new FormData()
    body.append('security_key', '')

    this.axios
      .post('', body, options)
      .then((response) => {
        console.log(response.data)
        this.lates_project = response.data.lates_project
        this.about_us = response.data.about_us
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>

<style scoped></style>
