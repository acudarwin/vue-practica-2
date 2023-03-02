<template lang="">
    <div id="container" class="container">
        <div class="row">
            <h3>{{product.nombre}}</h3>
        </div>
        <div class="row">
            <div class="col-12 col-sm-6 col-md-4 ">
                <img v-bind:src="product.imagen"
                    alt="">
            </div>
            <div class="col-12 col-sm-6  col-md-8">
                <h6 v-html="product.descripcion"></h6>
                <div class="p-3 mb-2 text-white" :style="precioEstilos">
                    Precio: {{product.precio}} BOB
                </div>
                <h5>Color</h5>
                <div v-if="product">
                    <div v-on:click="colorElegido=color" class="color-box clic" v-for="color in product.colores" :style="{'background': color}" :key="color"></div>
                </div>
                <h5>Cantidad</h5>
                <div class="quantity">
                    <button v-on:click="decrement">-</button> <div>{{counter}}</div> <button v-on:click="increment">+</button>
                </div>
                <div class="buy-box">
                    <button @click="() => addCart(product)" type="button" class="btn btn-primary" v-if="counter >= 0" :disabled="counter < 1 || colorElegido==''">Comprar</button>
                </div>
                
            </div>
        </div>
    </div>

</template>
<script>
import { ref } from 'vue'

export default {
    props: {
        product: {
            type: Object,
            required: true
        }
    },
    setup() {
        const addCart = (product) => {
            alert(JSON.stringify({id: product.id, name: product.nombre, cantidad: counter.value, color: colorElegido.value}))
        }
        const counter = ref(0)
        const colorElegido = ref('')
        return {
            precioEstilos: "background: orangered; color: white; font-weight: bold",
            counter,
            increment() {
                this.counter += 1
            },
            decrement() {
                this.counter -= 1
            },
            addCart,
            colorElegido
        }
    }
    
}
</script>
<style lang="css">
.quantity button{
                border-radius: 50%;
                display: inline-block;
                width: 30px;
            }
            .quantity div{
                text-align: center;
                min-width: 30px;
                display: inline-block;
                font-weight: bold;
            }
            .buy-box{
                margin: 20px;
            }
            img {
                width: 100%;
            }
    
</style>