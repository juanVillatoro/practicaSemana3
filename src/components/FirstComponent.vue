<template>
    <div class="firstcomponent">
        <img v-on:mousemove="getXY" alt="Vue logo" src="../assets/logo.png">
        <h1 v-on:mousemove="getXY" @mouseover="mouseOver" @mouseout="mouseOut"
        >   
            {{ titulo }}
        </h1>
        <h3 :style="[styleE,{'fontSize':fontSize+'px'}]">{{ materia }}</h3>
        <p>Tamaño de la fuente {{ fontSize }}</p>
        <button v-on:click="fontSize++">Incrementar</button>
        <button v-on:click="fontSize--">Disminuir</button>

        <h4>{{x}}, {{y}}</h4>
        <b>{{message}}</b>

    </div>
</template>
<script>
    export default {
        name: 'FirstComponent',
        data() {
            return{
                titulo: 'Mi primer componente',
                materia:'Programacion Computacional IV',
                x:0,
                y:0,
                message:'',
                fontSize:10,

            }
        },
        methods:{
            getXY(event){
                this.x=event.offsetX;
                this.y=event.offsetY;
            },
            mouseOver(){
                this.message = "IN"
            },
            mouseOut(){
                this.message = "OUT"
            },
        },
        computed:{
            styleE(){
                return{
                    textDecoration: 'underline',
                    textWeigth: 'bold'
                }
            }
        }
    }
</script>
