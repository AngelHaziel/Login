<script>
    import Navegador from './Navegador.svelte';
    import Login from './Login.svelte';
    //let arreglo = ['Home', 'About', 'Services', 'Contact', 'Enlace 5', 'Enlace 6'];
</script>

<style>
    .fondo{
        background-size: cover;
        background-repeat: no-repeat;
        background-blend-mode: darken;
        /* Gwen */
        background-color: rgba(0, 0, 0, .05);
        background-image: url('/src/images/gwen.jpg');
        /* Sett */
        /* background-position: 50% 40%;
        background-color: rgba(0, 0, 0, .05);
        background-image: url('/src/images/sett-dragon-obsidiana.jpg'); */
        /* Spider-Men */
        /* background-position: 50% 40%;
        background-color: rgba(0, 0, 0, .3);
        background-image: url('/src/images/spider-men.jpg'); */
        height: 100vh;
    }
</style>

<div class="fondo">
    <!-- <Navegador arregloInicial = {arreglo}/> -->
    <Navegador />
    <Login />
</div>
