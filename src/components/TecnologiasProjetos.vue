<script lang="ts">
import { defineComponent } from 'vue';
import tech1 from '../assets/imagens/tech1.png'
import tech2 from '../assets/imagens/tech2.png'
import tech3 from '../assets/imagens/tech3.png'

export default defineComponent({
    name: "tecnologias",
    data() {
        return {
            techList: [tech1, tech2, tech3]
        };
    }

})
</script>
<template>
    <section>
        <div class="tecnologias">
            <div class="title">
                <h2>TECNOLOGIAS UTILIZADAS</h2>
            </div>
            <ul>
                <div class="icones-tecnologias">
                    <i class="fa-brands fa-figma fa-4x pt-2" style="color: #A55EFF;"></i>
                </div>
                <div class="icones-tecnologias">
                    <i class="fa-brands fa-html5 fa-5x" style="color: #E5532D;"></i>
                </div>
                <div class="icones-tecnologias">
                    <i class="fa-brands fa-css3-alt fa-5x" style="color: #379AD6;"></i>
                </div>

                <div class="icones-tecnologias">
                    <i class="fa-brands fa-js fa-5x" style="color: #F0DB4E;"></i>
                </div>
                <div class="icones-tecnologias">
                    <i class="fa-brands fa-python fa-5x" style="color: #379AD6;"></i>
                </div>
            </ul>

        </div>
    </section>

</template>

<style scoped>
section {
    margin-top: 65px;
    width: 100%;
    display: flex;
    justify-content: center;
}

.tecnologias {
    width: 1160px
}

.title-tecnologia {
    display: flex;
    width: 100%;
    justify-content: start;
}

h2 {
    font-family: 'Exo 2';
    color: #003D73;
    font-size: 2.25rem;
    font-weight: 700;
    line-height: 36px;
    margin-left: 4px;
}

.title-tecnologia::before {
    content: '';
    display: inline-block;
    width: 7px;
    height: 35px;
    background: linear-gradient(180deg, #FF9F16 0%, #FCCC04 71%);
}

ul {
    display: flex;
    gap: 21px;
    margin: 21px 0 77px 0;

}

img {
    width: 80px;
}

@media (max-width: 768px) {
    section {
        margin-top: 39px;
    }

    img {
        max-width: 41px;
    }

    ul {
        margin-bottom: 29.3px;
    }

}
</style>