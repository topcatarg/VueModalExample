<template>
    <div id="app">
        <!--
        <b-row class="Cabecera">
            <b-col cols="2">
                <b-img fluid src="./assets/logoAfip.png" class="m-3" />
            </b-col>
        </b-row>
            -->
        <Grilla></Grilla>


    </div>
</template>

<script>
    import componente1 from './components/GridAndModal.vue'

    export default {
        name: 'Aplicacion',
        components: {
            'Grilla': componente1
        }
    }
</script>