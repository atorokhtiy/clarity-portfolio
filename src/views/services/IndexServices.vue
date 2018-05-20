<template>
  <div id="IndexServices" class="body--wrapper">
    <!-- SUB HEADER TOP -->
		<section class="sub--header">
			<div class="container">
				<div class="row">
					<div class="col-md-8">
						<div class="box-desc">
							<div class="title">
								Services we are providing
							</div>
							<div class="description">
								Here you can find information about our services. For more, please, contact us.
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
		<!-- NAV TARGET -->
		<section id="navigation-type-service" class="nav-target">
			<div class="container">
				<div class="row">
					<div class="col-md-12">
						<div class="box-list-nav">
							<ul>
								<li>
									<a class="jump-target" data-target-jump="#bussinessprocess">Bussines Proces</a>
								</li>
								<li>
									<a class="jump-target" data-target-jump="#company-profile">Company Profile</a>
								</li>
								<li>
									<a class="jump-target" data-target-jump="#ecommerce">E-Commerce</a>
								</li>
							</ul>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.NAV TARGET -->
		<!-- PROCESS BUSSINESS -->
		<section id="bussinessprocess" class="section--wrapper service-page-wrapper bg-white">
			<div class="container">
				<div class="row">
					<div class="col-md-12">
						<div class="title--top">
							<div class="title">
								PROCESS BUSSINES/AGILE PROJECT MANAGEMENT
							</div>
							<div class="description">
								We are using latest collaboration methodologies. Here how it is works.
							</div>
						</div>
					</div>
				</div>
				<div class="row">
					<div class="col-md-12">
						<div class="service-wrapper__image-process">
							<img src="static/images/gallery/agile.png" alt="">
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.PROCESS BUSSINESS -->
		<section id="company-profile" class="service-page-wrapper bg-grey2">
			<div class="container">
				<div class="row">
					<div class="service-wrapper__info-service">
						<div class="col-md-6">
							<div class="service-info">
								<div class="title">
									Company Profile
								</div>
								<div class="description">
									Our dedicated Team is the best.
								</div>
							</div>
						</div>
						<div class="col-md-6">
							<div class="image-info">
								<img src="static/images/service/company-profile.png" alt="">
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
		<section id="ecommerce" class="service-page-wrapper bg-white">
			<div class="container">
				<div class="row">
					<div class="service-wrapper__info-service">
						<div class="col-md-6">
							<div class="image-info">
								<img src="static/images/service/ecommerce.png" alt="">
							</div>
						</div>
						<div class="col-md-6">
							<div class="service-info">
								<div class="title">
									E-Commerce
								</div>
								<div class="description">
									We are using latest E-Commerce tools for support your order.
									<ul class="no_bullet">
										<li class="check">Fast contact with our team.</li>
										<li class="check">Track your order status.</li>
										<li class="check">Best deals.</li>
										<li class="check">Automated Bills</li>
									</ul>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
  </div>
</template>

<script>
export default {
  name: 'IndexServices',
  data () {
    return {
      our_services: [],
      teknologi: []
    }
  },
  created () {
    let _self = this
    let options = {
      headers: {
        'Content-Type': 'multipart/form-data',
        'Api-Key': ''
      }
    }

    let body = new FormData()
    body.append('security_key', '')

    _self.axios.all([
      _self.axios.post('', body, options),
      _self.axios.post('', body, options)
    ])
    .then(
      _self.axios.spread(
        (dashboard, service) => {
          console.log(dashboard.data.teknologi)
          console.log(service.data.our_services)
          _self.teknologi = dashboard.data.teknologi
          _self.our_services = service.data.our_services
        }
      )
    )
    .catch((error) => {
      console.log(error)
    })
  }
}
</script>

<style scoped></style>
