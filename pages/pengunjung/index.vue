<template>
  <div class="container-fluid">
      <div class="row py-5 d-flex justify-content-center">
          <div class="col-lg-11">
          <nuxt-link to="/pengunjung/tambah">
              <div class="card bg-pengunjung rounded-5">
                  <div class="card-body">
                      <h2 class="fw-bold">Pengunjung</h2>
                  </div>
              </div>
          </nuxt-link>
      </div>
  </div>

  <div class="row py-5 d-flex justify-content-center">
      <div class="col-lg-11">
          <nuxt-link to="/buku">
          <div class="card bg-buku rounded-5">
              <div class="card-body">
                  <h2 class="fw-bold">Buku</h2>
              </div>
          </div>
          </nuxt-link>
      </div>
  </div>
          </div>
</template>

<style scoped>
.container-fluid {
  background-color: #C49DC0;
}
.card {
  height: 250px;
  box-shadow: 1px 1px 10px hsl(0, 0%, 100%)
}
.card.bg-pengunjung {
  background-image: url('@/assets/img/pengunjung.jpeg');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
.card.bg-buku {
  background: url('@/assets/img/bg-home.jpg') no-repeat center center;
  background-size: cover;

}

h2{
  color: rgb(255, 255, 255);
}
</style>
