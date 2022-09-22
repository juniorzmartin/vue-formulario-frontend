<template>
    <div>
        <i v-for="estrela in estrelas" :class="estrela.estilo" :key="estrela.id"></i>
        {{estrelas}}
        <i class="bi bi-star-fill"></i>
    </div>
</template>

<script>
export default {
    name: 'InputEstrelas',
    props: {
        numeroEstrelas: {
            type: Number,
            required: true
        }
    },
    data: () => ({
        estrelas: []
    }),
        created() {
        this.iniciarEstrelas()
    },
    methods: {
        iniciarEstrelas() {
            for(let i = 0; i < this.numeroEstrelas; i++){
                this.estrelas[i] = {id: i, estilo:'bi bi-star estrela'}
            }
        }
    }
}
</script>

<style scoped>
.estrela {
    font-size: 1.5rem;
    color:#999;
    margin-left: 2px;
    margin-right: 1px;

}
</style>