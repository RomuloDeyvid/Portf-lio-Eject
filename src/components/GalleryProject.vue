<script lang="ts">
import { defineComponent } from 'vue';
import image1 from '../assets/imagens/image1.png';
import image2 from '../assets/imagens/image2.png'
import image3 from '../assets/imagens/image3.png'
import image4 from '../assets/imagens/image4.png'
import image5 from '../assets/imagens/image5.png'

export default defineComponent({
    name: 'ImageGallery',
    data() {
        return {
            currentImage: image1,

            thumbnails: [
                image1,
                image2,
                image3,
                image4,
                image5,
            ],
        };
    },
    methods: {
        setImage(imageUrl: string) {
            this.currentImage = imageUrl;
        }
    },
    computed: {
        filteredThumbnails() {
            return this.thumbnails.filter(thumb => thumb !== this.currentImage)
        }
    }
}

)

</script>

<template>
    <section>
        <div class="title">
            <h2>GREEN GARDENS</h2>
        </div>
        <div class="content-gallery">

            <div class="image-gallery">
                <!-- Imagem Grande -->
                <div class="large-image">
                    <img :src="currentImage" alt="Imagem Grande">
                </div>

                <!-- Miniaturas -->
                <div class="thumbnails">
                    <img v-for="(thumb, index) in filteredThumbnails" :key="index" :src="thumb" alt="miniatura"
                        @click="setImage(thumb)" :class="{ 'selected-thumbnail': currentImage === thumb }"
                        class="thumbnail-image" />
                </div>
            </div>
            <div class="textGallery">
                <p>Green gardens é uma empresa de paisagismo que está iniciando no mercado e decidiu começar com sua
                    presença online através de um site. O projeto elaborado pela EJECT teve 3 meses de duração, onde
                    fizemos um trabalho de elaboração de identidade visual e sua aplicação no site para atender as
                    demandas de nosso cliente.</p>
                <a href="https://juliosoares.pythonanywhere.com "><button>VER MAIS</button></a>
            </div>
        </div>
    </section>

</template>

<style scoped>
section {
    padding-top: 131px;
}

.content-gallery {
    max-width: 1160px;
    background-color: white;
    display: flex;
    margin-top: 37px;
}

.image-gallery {
    max-width: 760px;
}

.large-image {
    max-width: 760px;
    height: 504px;
}

.thumbnails {
    display: flex;
    justify-content: space-between
}

.thumbnails img {
    max-width: 160px;
    height: 123px;
    cursor: pointer;
}

.thumbnail-image.selected-thumbnail {
    transform: scale(1.2);
    border: 2px solid #003D73;
}

.textGallery {
    max-width: 360px;
    height: 504px;
    margin-left: 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.textGallery p {
    font-family: 'Montserrat';
    font-style: normal;
    font-weight: 400;
    font-size: 20px;
    line-height: 30px;

    color: #000000;
}

.textGallery button {
    width: 164px;
    height: 40px;
    background: #003D73;
    font-size: 25px;
    line-height: 30px;
    font-family: 'Exo 2';
    color: #ffffff;
    border-radius: 10PX;
}

@media (max-width: 880px) {
    .image-gallery {
        max-width: 100%;
    }

    .thumbnails img {
        max-width: 100px;
        max-height: 90px;
    }

    .large-image {
        max-width: 600px;
        height: auto;
    }

    .textGallery {
        height: auto;
        padding-right: 10px;
    }
}


@media (max-width:768px) {
    .content-gallery {
        flex-direction: column;
        max-width: 600px;
    }

    .textGallery {
        max-width: 600px;
        margin: 0;
    }

    section {
        padding: 24px;
        width: 100%;
    }

    .large-image {
        max-width: 100%;
    }

    .thumbnails img {
        max-width: 70px;
        height: 62px;
    }

    .thumbnails {
        max-width: 600px;
    }

    .textGallery p {
        margin-top: 14px;
        font-size: 0.75rem;
        font-weight: 400;
        line-height: 16.43px;
    }

    .textGallery button {
        display: none;
        /* font-size: 0.9rem;
        width: 100px;
        height: 30px;
        margin-top: 10px; */
    }
}
</style>