<template>
    <div class="content">
        <div class="container-fluid">
            <nuxt-link to="/buku" class="btn btn-outline-dark btn-lg mt-4">KEMBALI</nuxt-link>
                <nuxt-link to="/" class="btn btn-outline-dark btn-lg mt-4 ms-3">SELESAI</nuxt-link>
                    <h2 class="text-center my-4 ">RINCIAN BUKU</h2>
            <div class="row d-flex justify-content-center flex-md-wrap" style="padding-top: 50px;">
                <div class="col-3 ">
                    <img :src="buku?.cover"  class="cover row img-fluid" alt="cover buku"   style="width: 250px; padding-top: 100px;">
                    <div class="row">
                    </div>
                </div>
                <div class="col-8">
                    <div class="row">
                        <h1 class="text start text-center my-4">{{ buku?.judul }}</h1>
                    </div>
                    <div class="row">
                    <div class="badge bg-secondary class p-2">{{ buku?.kategori?.nama }}</div>
                        <ul class="list-group list-group-flush">
                            <li class="list-group-item">JUDUL: {{ buku?.penulis }}</li>
                            <li class="list-group-item">PENULIS: {{ buku?.penerbit }}</li>
                            <li class="list-group-item">TAHUN TERBIT: {{ buku?.tahun_terbit }}</li>
                            <li class="list-group-item">RAK: {{ buku?.rak }}</li>
                            <li class="list-group-item">KATEGORI: {{ buku?.kategori?.nama }}</li>
                            <li class="list-group-item">DESKRIPSI: {{ buku?.deskripsi }}</li>
                        </ul>                       
                    </div>
                    <div class="row">
                    </div>
                </div>
            </div>
        </div>
        </div>
</template>
<script setup>


const supabase = useSupabaseClient()
const route = useRoute()
const buku = ref()

const getBookByid = async () => {
    const { data, error } = await supabase
    .from('buku')
    .select(`*, kategori(*)`)
    .eq('id', route.params.id)
    .maybeSingle()
    if(data) buku.value = data

}

onMounted(() => {
    getBookByid()
})

</script>
<style>
.content {
background-image:linear-gradient(#C49DC0);
background-size: cover;
width: 100%;
height: 100vh;
font-family: '';
color: #343D84(135, 135, 135);
}
</style> 