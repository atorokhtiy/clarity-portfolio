<template>
  <div id="ShowPortofolio" class="body--wrapper">
    <section class="section--wrapper">
      <div class="container">
        <div class="row">
          <div class="col-md-8 col-md-offset-2">
            <div class="panel panel-default">
              <div class="panel-body">
                <div class="text-center">
                  <h3>{{ msg }} - {{ this.$route.params.id }}</h3>
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
  name: 'ShowPortofolio',
  data () {
    return {
      msg: 'show portofolio'
    }
  }
}
</script>

<style scoped></style>
