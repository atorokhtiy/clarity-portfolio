<template>
  <div id="IndexAbouts" class="body--wrapper">
    <!-- SUB HEADER TOP -->
		<section class="sub--header diagonal-shadow mg-bottom-diagonal">
			<div class="container">
				<div class="row">
					<div class="col-md-8">
						<div class="box-desc">
							<div class="title">
								About us
							</div>
							<div class="description">
								Computers wholesale, peripheral equipment and software
							</div>
							<br>
							<router-link :to="'apply-project'" class="btn btn-lg btn-warning">
							  Request portfolio
							</router-link>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.SUB HEADER TOP -->
		<!-- ABOUT US -->
		<section class="section--wrapper bg-white">
			<div class="container">
				<div class="row">
					<div class="col-md-12">
						<div class="box-information" v-if="about_us">
							<div class="title--top">
								<div class="title">
									{{ about_us.title }}
								</div>
								<div class="description">
									{{ about_us.short_desc }}
								</div>
							</div>
						</div>
					</div>
				</div>
				<div class="row">
					<div class="col-md-12">
						<div class="text-center">
							<a href="#" class="btn btn-lg btn-danger">
								COMPANY PROFILE DOWNLOAD
							</a>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.ABOUT US -->
		<!-- OUR TEAM -->
		<section class="section--wrapper about-us">
			<div class="container">
				<div class="row">
					<div class="col-md-12">
						<div class="title--top">
							<div class="title txt-white">
								Request portfolio
             </div>
						</div>
					</div>
				</div>
				<div class="row text-center">
					<div class="col-md-12">
						<div class="box-list-team" v-for="t in team" v-bind:key="t.name">
							<div class="box-list-team__image">
								<img :src='t.foto_url' alt="">
							</div>
							<div class="box-list-team__name">
								{{ t.name }}
							</div>
							<div class="box-list-team__position">
								{{ t.position }}
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
		<!-- /.OUR TEAM -->
  </div>
</template>

<script>
export default {
  name: 'IndexAboutus',
  data () {
    return {
      about_us: {},
      team: []
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
        this.about_us = response.data.about_us
        this.team = response.data.team
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>

<style scoped></style>
