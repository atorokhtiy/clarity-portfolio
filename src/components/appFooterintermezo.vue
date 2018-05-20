<template>
	<div id="Footerintermezo">
		<section class="intermezo-footer">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <div class="pull-left">
              <div class="box-info">
                <div class="title">
                  Request Portfolio
                </div>
                <div class="description">
                  Latest company updates.
                </div>
              </div>
            </div>
            <div class="pull-right">
              <router-link :to="'portofolios'" class="btn btn-lg btn-danger">
                <i class="fa fa-eye"></i>
                Request portfolio
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>
	</div>
</template>

<script>
	export default { name: 'appFooterintermezo' }
</script>
