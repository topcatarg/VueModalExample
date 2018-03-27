<template>
    <div id="blocks">
        <b-container>
            <div class="cards">
                <div class="card" v-for="card in cards">
                    <img :src="card.image" :alt="card.mainTitle">
                    <div class="card-content">
                        <h5>{{card.mainTitle}}</h5>
                        <p>{{card.text}}</p>
                        <a href="javascript:void(0)" @click="showModal(card.index)">Learn More</i></a>
                    </div>
                </div>
            </div>
        </b-container>
        <b-modal ref="modal" centered hide-footer>
            <div class="d-block text-center">
                <h3>{{this.modalShow.mainTitle}}</h3>
                <p>{{this.modalShow.modalText}}</p>
            </div>
        </b-modal>
        <b-button @click="modalShow = !modalShow">
            Open Modal
        </b-button>
    </div>
</template>

<script>
    export default {
        name: 'GridAndModal',
        data() {
            return {
                cards: [
                    {
                        image: '../../assets/image1.jpg',
                        mainTitle: 'Title1',
                        text: 'Text1',
                        modalText: 'Modal text content1',
                        index: 0
                    },
                    {
                        image: '../../assets/image2.jpg',
                        mainTitle: 'Title2',
                        text: 'Text2',
                        modalText: 'Modal text content2',
                        index: 1
                    },
                    {
                        image: '../../assets/image3.jpg',
                        mainTitle: 'Title3',
                        text: 'Text3',
                        modalText: 'Modal text content3',
                        index: 2
                    }
                ],
                modalShow: false,
                ModalCard: {}

            }
        },
        methods: {
            showModal(index) {
                console.debug(index);
                this.modalShow = this.cards[index];
                this.$refs.modal.show()
            },
            hideModal() {
                this.$refs.modal.hide()
            }
        }
    }
</script>

<style>
    nav.navbar.shrink {
        max-height: 10px;
    }
</style>
