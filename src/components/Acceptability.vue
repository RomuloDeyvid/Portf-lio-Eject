<template>
    <section>
        <div class="firs-coll">
            <div class="content">
                <div class="title">
                    <h2>ACEITABILIDADE</h2>
                </div>
                <div>
                    <img src="../assets/imagens/indice.pgn" alt="">
                    <p>
                    Você indicaria os serviços da EJECT para um amigo?
                </p>
                </div>
                
                <p>
                    Como você avalia o time de desenvolvimento?
                </p>
                <p>
                    Como você avalia a entrega final?
                </p>
            </div>
        </div>
        <div class="second-coll">
            <Graphic/>
            
        </div>
    </section>

</template>

<script setup lang="ts">
import Graphic from './Graphic.vue';


</script>

<style scoped>
    section{
        height: 574px;
        background-color:#A9E1FF;
        display: grid;
        grid-template-columns: 50% 50%;
    }
    .firs-coll{
        background: #0787CB;
        height: 100%;
        border-radius: 0 10px 10px 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .content{
        display: flex;
        flex-direction: column;
        gap: 20px;
    }

    .title{
        width: 400px;
        margin-bottom: 26px;
    }
    p{
        font-family: 'Montserrat';
        font-size: 1.25rem;
        font-weight: 600;
        color: #FFFFFF;
        width: 330px;
        
    }
   
    .second-coll{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }
    
</style>