<template>
    <div class="container">
        <div class="row">
            <h3>{{ producto.nombre }}</h3>
        </div>
        <div class="row">
            <div class="col-12 col-sm-6 col-md-4 ">
                <img v-bind:src="producto.imagen" alt="im"  :style="{width: '100%'}">
          
            </div>

            <div class="col-12 col-sm-6  col-md-8 display:flex">
                <h6 v-html="  producto.descripcion "></h6>
                <div class="p-3 mb-2 text-white" style="background-color: orangered;">
                    <b> Precio: {{ producto.precio }} BOB</b>
                </div>
                <h5>Color</h5>
                    <div class="flex-container">
                        <div v-for="c in producto.colores" v-bind:key="c">
                            <div  @click="selecolor(c)" class="color-box clic"  v-bind:style="{backgroundColor:c} " ></div>
                        </div>
                    </div>
                <h5>Cantidad</h5>
                <div class="quantity">
                    <button @click="contador(-1)">-</button>
                    <div>{{ valor }}</div>
                    <button @click="contador(1)">+</button>
                </div>

                <div class="buy-box">
                    <button id="btncomprar" type="button" class="btn btn-primary" v-on:click="comprar" >Comprar</button>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
import img1 from '@/assets/dron_LU3_MAX_GPS_8K_HD.png'
export default {
    name: 'MenuLateral',
    props: {
        msg: String
    },
    data() {
        return {
            producto:
            {
                id: 1,
                imagen: img1,
                nombre: "Dron LU3 MAX GPS 8K HD",
                descripcion: "Dron LU3 MAX GPS 8K HD profesional con <b>cámara Dual</b>,cardán autoestabilizador, Motor sin escobillas para evitar obstáculos, cuadricóptero plegable",
                precio: "620",
                colores: ["red", "blue", "black", "yellow"]
            },
            pedido:
            {
                id:null,
                cantidad: 1,
                color:null
            },
            valor: 0,
            colorsel:''
        }
    },
    methods:{
        contador(v){
            this.valor+=v
        },
        selecolor(c){
            this.colorsel=c
        },
        comprar: function (event) {
            // `this` dentro de los métodos apunta a la instancia de Vue
            //alert('Hola ' + this.valor + '!')
            // `evento` es el evento DOM nativo
            if (event) {
            alert('id prod: ' + this.producto.id+ ', Cantidad: '+this.valor+ ', Color seleccionado: '+this.colorsel)

            }
        }
    }
}
</script>
<style>
.flex-container {
    display: flex;
}
</style> 
