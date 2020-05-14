<template>
    <popper trigger="clickToToggle"
            @show="show"
            :options="{
                  placement: 'top',
                  modifiers: {
                        name: 'offset',
                      options: {
                        offset: ['10px', '80px'],
                      }
                  }
                }" class="popover">

        <div class="popper">

            <div class="popover__header">
                <div class="option-block__title">
                    Видео-инструкция
                </div>

                <div class="popover__close"  @click="close">
                    Закрыть
                    <div class="popover__close-icon">
                        <img src="../assets/images/icons/close.svg" alt="close-icon">
                    </div>
                </div>
            </div>

            <div class="popover__content">

                <div class="product-slider">

                    <div class="product-slider__item product-slider__item_full-height">
                        <VueSlickCarousel :arrows="true" :fade="true" :infinite="true" :dots="true">
                            <slot name="slide-items">
                                <div class="product-slider__img"><img src="../assets/images/popover-img.png"/></div>
                            </slot>
                        </VueSlickCarousel>
                    </div>

                </div>
            </div>

        </div>

        <span class="btn-group__item_preview" slot="reference" >
            <img src="../assets/images/icons/eye.svg" alt="icon-eye">
        </span>
    </popper>
</template>

<script>
    import VueSlickCarousel from 'vue-slick-carousel';
    import Popper from 'vue-popperjs';

    export default {
        name: "Popover",
        components: {
            VueSlickCarousel,
            'popper': Popper
        },
        data() {
            return {
                openedPopper: null
            }
        },
        methods: {
            close() {
                if(this.openedPopper) {
                    this.openedPopper.doClose();
                }
            },
            show(event) {
                this.openedPopper = event;
            }
        }

    }


</script>

<style lang="scss">
</style>