<template>
    <div id="banner" class="d-flex align-items-center" role="img" alt="Banner de um hámburguer realista e saboroso" >
        <h1 class="bg-dark text-light p-4 text-bold rounded-3">Make your Burguer!</h1>
    </div>
</template>

<script>
export default {
    name: 'Banner'
}
</script>

<style scoped>
    #banner{
        background: url('/img/burger-cut.jpg') no-repeat;
        background-size: cover;
        background-position: 0px -120px ;
        height: 400px;
    }

        @media(max-width: 850px) {
        #banner{
            background-position: -130px -120px ;
        }
    }

    @media(max-width: 640px) {
        #banner{
            background-position: -300px -120px ;
        }
    }

     @media(max-width: 400px) {
        #banner{
            background-position: -350px -120px ;
        }
    }
</style>