<script lang="ts">
import Tag from './Tag.vue';


    export default{
    props: {
        ingrediente: { type: String, required: true },
    },
    data() {
        return {
            selecionado: false
        };
    },
    methods: {
        aoClicar(){
            this.selecionado = !this.selecionado;
            if(this.selecionado){
                this.$emit('adicionaringrediente', this.ingrediente)
            }else{
                this.$emit('removerIngrediente', this.ingrediente)
            }
        }

    },
    emits:['adicionaringrediente', 'removerIngrediente'],
    components: { Tag }
}

</script>


<template>
    <button @click="aoClicar" :aria-pressed="selecionado"> 
        <Tag :ingrediente="ingrediente" :ativa="selecionado"/>
    </button>
</template>