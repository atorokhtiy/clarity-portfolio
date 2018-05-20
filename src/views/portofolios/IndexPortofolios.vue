<template>
  <div id="IndexPortofolios" class="body--wrapper">
    <!-- SUB HEADER TOP -->
		<section class="sub--header diagonal-shadow mg-bottom-diagonal">
			<div class="container">
				<div class="row">
					<div class="col-md-8">
						<div class="box-desc">
							<div class="title">
								Portofolio
							</div>
							<div class="description">
								Here you can see our latest projects. For more information, please, contact us.
							</div>
							<br>
              <router-link :to="'apply-project'" class="btn btn-lg btn-warning">
							  Contact us
							</router-link>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.SUB HEADER TOP -->
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
        <div class="col-md-6">
          <div class="service-info">
            <div class="title">
              Recent deals:
            </div>
            <div class="description">
              <ul class="no_bullet">
                <li class="check">Winner in 3 state orders on total: 645 122.00 UAH.</li>
                <li class="check">3 contracts signed on total: 645 122.00 UAH..</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="row">
					<div class="col-md-12">
						<div class="service-wrapper__image-process">
							<img src="static/images/gallery/orders.png" alt="">
						</div>
					</div>
				</div>
				<div class="row">
          <div class="col-md-3" v-for="project in portofolio" v-bind:key="project.id">
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
			</div>
		</section>
		<!-- /.LATEST-PROJECT -->
  </div>
</template>

<script>
export default {
  name: 'IndexPortofolios',
  data () {
    return {
      portofolio: []
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
        this.portofolio = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>

<style scoped></style>
