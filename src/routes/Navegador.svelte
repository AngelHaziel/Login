<script>
    //valores por default
    export let arregloInicial = ['Inicio', 'Acerca', 'Servicios', 'Contacto'];
    //inicialización de variable con valor de arregloInicial
    let enlaces = arregloInicial;
</script>

<style>
    *{
      font-family: 'Poppins', sans-serif;  
    }

    header{
        position: fixed;
        top: 0;
        left: 0;
        width: 90%;
        padding: 10px 100px;
        /* background-color: rgba(0, 0, 0, 0.3); */
        background: linear-gradient(rgba(0, 0, 0, .7), transparent);
        display: flex;
        justify-content: space-between;
        align-items: center;
        z-index: 10;
    }

    .logo{
        font-size: 2em;
        color: #fff;
        user-select: none;
    }

    .navegador a{
        position: relative;
        font-size: 1.3em;
        color: #fff;
        text-decoration: none;
        font-weight: 500;
        margin-left: 40px;
    }

    .navegador a::after{
        content: '';
        position: absolute;
        left: 0;
        bottom: -6px;
        width: 100%;
        height: 3px;
        background-color: #fff;
        border-radius: 5px;
        transform-origin: center; /* right */
        transform: scaleX(0);
        transition: transform .5s;
    }

    .navegador a:hover::after{
        transform-origin: center; /* left */
        transform: scaleX(1);
    }

    .navegador .btnLogin-popup{
        width: 130px;
        height: 50px;
        background-color: transparent;
        border: 2px solid #fff;
        outline: 0;
        border-radius: 6px;
        cursor: pointer;
        font-size: 1.3em;
        color: #fff;
        font-weight: 500;
        margin-left: 40px;
        transition: .5s;
    }

    .navegador .btnLogin-popup:hover{
        background-color: #fff;
        color: #162938;
    }
</style>

<header>
    <h2 class="logo">Logo</h2>
    <nav class="navegador">
        {#each enlaces as enlace}
            <a data-sveltekit-preload-data="tap" href=" ">{enlace}</a>
        {/each}
        <button class="btnLogin-popup">Login</button>
    </nav>
</header>