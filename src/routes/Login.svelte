<script>
    let correo = "";
    let contra = "";

    let mostrarUsuarios = () => {
        fetch('http://localhost/apiPHP/')
        .then(respuesta=>respuesta.json())
        .then((objetosJSON)=>{
            let usuarios = [] = objetosJSON;

            console.log(usuarios);

        }).catch(console.log);
    }
    mostrarUsuarios();

    let verificacionLogin = () => {
        fetch('http://localhost/apiPHP/')
        .then(respuesta=>respuesta.json())
        .then((objetosJSON)=>{
            let usuarios = [] = objetosJSON;
            let i = 0;
            while(i < usuarios.length){
                if(correo == usuarios[i].correo){
                    if(contra == usuarios[i].contra){
                        console.log(usuarios[i].nombre + " inicio sesión");
                        alert(usuarios[i].nombre + " inicio sesión");
                        break;
                    } else {
                        console.log("Datos incorrectos");
                        alert("Datos incorrectos");
                        break;
                    }
                }
                i++;
            }
            if(i == usuarios.length){
                console.log("No se ha encontrado al usuario");
                alert("No se ha encontrado al usuario");
            }
            
        }).catch(console.log);
    }

</script>

<style>
    *{
      font-family: 'Poppins', sans-serif;
    }

    .contenedor{
        /* background-color: transparent; */
        /* background: rgba(255, 255, 255, 0.15); */
        width: 400px;
        height: 440px;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        top: 22%;
        left: 36%;
        border: 3px solid rgba(255, 255, 255, .5);
        border-radius: 20px;
        backdrop-filter: blur(10px);
        box-shadow: 0 0 30px rgba(0, 0, 0, .5);
        overflow: hidden;
    }

    .contenedor .cuadro-formulario{
        width: 100%;
        padding: 40px;
    }

    .contenedor .icono-cerrar{
        position: absolute;
        top: 0;
        right: 0;
        width: 45px;
        height: 45px;
        background: #48c5ff;
        /* background: #ff8c00; */
        font-size: 2em;
        color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        border-bottom-left-radius: 20px;
        cursor: pointer;
        z-index: 1;
    }

    .cuadro-formulario h2{
        margin-top: 0;
        font-size: 2em;
        /* color: #fff; */
        color: #48c5ff;
        /* color: #ff8c00; */
        text-align: center;
    }

    .entrada-datos{
        position: relative;
        width: 100%;
        height: 50px;
        border-bottom: 2px solid #fff;
        margin: 30px 0;
    }

    .entrada-datos label{
        position: absolute;
        top: 50%;
        left: 5px;
        color: rgba(255, 255, 255, 0.5);
        transform: translateY(-50%);
        font-size: 1.2em;
        font-weight: 500;
        pointer-events: none;
        transition: .5s;
    }

    .entrada-datos input:focus~label,
    .entrada-datos input:valid~label{
        top: -5px;
        color: rgba(255, 255, 255, .9);
    }

    .entrada-datos input{
        width: 100%;
        height: 100%;
        background: transparent;
        border: none;
        outline: none;
        font-size: 1.2em;
        font-weight: 600;
        padding: 0 35px 0 5px;
        color: #fff;
    }

    .entrada-datos .icono{
        position: absolute;
        right: 8px;
        bottom: 8px;
        font-size: 1.4em;
        color: #fff;
    }

    .recordar-contra{
        font-size: .9em;
        color: #fff;
        font-weight: 500;
        margin: -15px 0 25px;
        display: flex;
        justify-content: space-between;
    }

    .recordar-contra label input{
        accent-color: #fff;
        margin-right: 3px;
    }

    .recordar-contra a{
        position: relative;
        top: 3px;
        /* color: #48c5ff; */
        color: #fff;
        font-weight: bold;
        text-decoration: none;
    }

    .recordar-contra a:hover{
        text-decoration: underline;
    }

    .btn{
        width: 100%;
        height: 45px;
        /* background: #fff; */
        background: #48c5ff;
        /* background: #ff8c00; */
        border: none;
        outline: none;
        border-radius: 6px;
        cursor: pointer;
        font-size: 1em;
        /* color: #162938; */
        color: #fff;
        font-weight: 600;
        transition: 
            color 0.2s,
            background-color 0.2s;
    }

    .btn:hover{
        box-shadow: 0px 2px 10px 2px white;
        background-color: white;
        cursor: pointer;
        color: black;
        transition: 
            color 0.2s,
            background-color 0.2s;
    }

    .btn:active{
        color: white;
        background-color: rgba(255, 255, 255, .5);
        cursor: pointer;
        box-shadow: 0px 0px 10px 0px white;
        transition: 
            color 0.2s,
            background-color 0.2s;
    }

    .registro-login{
        font-size: .9em;
        color: white;
        text-align: center;
        font-weight: 500;
        margin: 20px 0 12px;
    }

    .registro-login p a{
        color: #48c5ff;
        /* color: #ff8c00; */
        text-decoration: none;
        font-weight: 600;
    }

    .registro-login p a:hover{
        text-decoration: underline;
    }

</style>

<div class="contenedor">
    <span class="icono-cerrar">
        <ion-icon name="close"></ion-icon>
    </span>
    <div class="cuadro-formulario login">
        <h2>Login</h2>
        <form action="">
            <div class="entrada-datos">
                <span class="icono">
                    <ion-icon name="mail"></ion-icon>
                </span>
                <input  type="mail" bind:value={correo} required>
                <label for="">Correo</label>
            </div>
            <div class="entrada-datos">
                <span class="icono">
                    <ion-icon name="lock-closed"></ion-icon>
                </span>
                <input type="password" bind:value={contra} required>
                <label for="">Contraseña</label>
            </div>
            <div class="recordar-contra">
                <label for="">
                    <input type="checkbox">Recordarme
                </label>
                <a data-sveltekit-preload-data="tap" href=" " >¿Olvidaste tu Contraseña?</a>
            </div>
            <button type="submit" class="btn" on:click|preventDefault={verificacionLogin}>Ingresar</button>
            <div class="registro-login">
                <p>¿No tienes cuenta? <a data-sveltekit-preload-data="tap" href=" " >Registrate</a></p>
            </div>
        </form>
    </div>
</div>