<template>
    <div class="demo">
        <CarouselCard ref="carouselCardRef" :interval="7000" :autoplay="false" height="260px" type="card" arrow="always"
            @change="changeHandle">
            <!-- Usar projetosFiltrados no v-for -->
            <CarouselCardItem v-for="(card, index) in projetosFiltrados" :key="card.id">
                <div class="card-carousel">
                    <img :src="card.path" :alt="card.name" class="w-full h-56 object-cover rounded-lg shadow">
                </div>
            </CarouselCardItem>
        </CarouselCard>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';
import { CarouselCard, CarouselCardItem } from './carousel-card';
import '../../../styles/index.css';
import type { ICarouselCard } from '../../../types/index';

export default defineComponent({
    name: 'container-carrousel',
    props: {
        tipoDeProjeto: {
            type: String,
            required: true
        }
    },
    components: { CarouselCard, CarouselCardItem },
    setup(props) {
        const carouselCardRef = ref<ICarouselCard>();

        const changeHandle = (index: number) => {
            console.log(index);
        };

        const sliders = ref([

            { id: 1, name: 'ADM Consult', path: '/imagens/adm-consult.png', type: 'Sites' },
            { id: 2, name: 'Observatório de desigualdades', path: '/imagens/ism.png', type: 'Sites' },
            { id: 3, name: 'Georisco', path: '/imagens/georisco.png', type: 'Sites' },
            { id: 4, name: 'Lumus', path: '/imagens/lumus.png', type: 'Sites' },
            { id: 5, name: 'Consej ', path: '/imagens/consej.png', type: 'Sites' },

            { id: 6, name: 'Literatura Brasileira Traduzida', path: '/imagens/literatura.png', type: 'Sistemas' },
            { id: 7, name: 'FBC Finanças', path: '/imagens/financas.png', type: 'Sistemas' },

            { id: 8, name: 'Tecno Diesel', path: '/imagens/tecno-diesel.png', type: 'E-commerce' },
            { id: 9, name: 'MCI Materiais Cirúrgicos', path: '/imagens/mci.png', type: 'E-commerce' },

            { id: 10, name: 'Affiliates', path: '/imagens/affiliates.png', type: 'Landing Pages' },
            { id: 11, name: 'Grãos de Mostarda', path: '/imagens/grao.png', type: 'Landing Pages' },
            { id: 12, name: 'Green Gardens', path: '/imagens/green.png', type: 'Landing Pages' },

        ]);

        // Computed property para filtrar os projetos com base no tipoDeProjeto
        const projetosFiltrados = computed(() => {
            if (props.tipoDeProjeto === 'Filtro') {
                return sliders.value;
            }
            return sliders.value.filter(slider => slider.type === props.tipoDeProjeto);
        });

        return {
            carouselCardRef,
            changeHandle,
            projetosFiltrados,
            sliders
        };
    }
});
</script>

<style scoped>
.demo {
    width: 70%;
    height: 28rem;
    margin: auto;
}

.card-carousel {
    height: 100%;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    color: #FFF;
}

.w-full {
    width: 100%;
    height: 100%;
}

@media (min-width: 360px) and (max-width: 599px) {
    .demo {
        width: 90%;
        height: 12rem;
    }
}

@media (min-width: 600px) and (max-width: 799px) {
    .demo {
        height: 14rem;
    }
}

@media (min-width: 800px) and (max-width: 999px) {
    .demo {
        height: 18rem;
    }
}

@media (min-width: 1000px) and (max-width: 1199px) {

    .demo {
        height: 20rem;
    }
}

@media (min-width: 1200px) and (max-width: 1399px) {

    .demo {
        height: 22rem;
    }

}

@media (min-width: 1400px) and (max-width: 1599px) {

    .demo {
        height: 22rem;
    }
}

@media (min-width: 1600px) and (max-width: 1800px) {

    .demo {
        height: 25rem;
    }
}

@media (min-width: 1800px) and (max-width: 1920px) {
    .demo {
        height: 25rem;
    }
}

@media (min-width: 1921px) and (max-width: 2048px) {
    .demo {
        height: 27rem;
    }
}

@media (min-width: 2049px) and (max-width: 2560px) {
    .demo {
        height: 31rem;
    }
}

@media (min-width: 2561) and (max-width: 3840px) {
    .demo {}
}
</style>