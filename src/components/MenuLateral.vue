<template>
    <nav class="navbar navbar-expand-lg" v-bind:style="{backgroundColor:configuracionPagina.menuColor}">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">{{ configuracionPagina.marca }}</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <div v-for="m in configuracionPagina.menus" v-bind:key="m">
                            <li class="nav-item">
                                <a class="nav-link" aria-current="page" href="#">{{ m.etiqueta }}</a>
                            </li>
                        </div>
                </ul>
            </div>
        </div>
    </nav>
</template>
<script>
export default {
    name: 'MenuLateral',
    props: {
        msg: String
    },
    data() {
        return {
            configuracionPagina: {
                marca:"MegaDron",
                menuColor:"lightblue",
                FooterColor:"slategrey",
                precioEstilos: "background: orangered; color: white; font-weight: bold",
                menus :[
                    {
                        etiqueta: "Inicio",
                        url: "?"
                    },
                    {
                        etiqueta:"Tienda",
                         url: "?"
                    }
                ]
            }
        }
    },
}
</script>
