<template>
	<div>
    <div id="header-corporate">
      <nav class="navbar navbar-default">
        <div class="container">
          <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar-menu-top" aria-expanded="false">
              <span class="sr-only">Toggle navigation</span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
              <span class="icon-bar"></span>
            </button>
            <router-link :to="'/'" class="navbar-brand">
               І – АР – СІ
            </router-link>
          </div>

          <div class="collapse navbar-collapse" id="navbar-menu-top">
            <ul class="nav navbar-nav navbar-right">
              <li><router-link :to="{ path: '/' }" exact="">Home</router-link></li>
              <li><router-link :to="{ path: '/about-us' }" exact="">About Us</router-link></li>
              <li><router-link :to="{ path: '/services' }" exact="">Services</router-link></li>
              <li><router-link :to="{ path: '/portofolios' }" exact="">Portofolio</router-link></li>
              <li><router-link :to="{ path: '/contact-us' }" exact="">Contact Us</router-link></li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
	</div>
</template>

<script>
	export default { name: 'appHeader' }
</script>
