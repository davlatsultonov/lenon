<template>
    <popper trigger="clickToToggle"
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
                    Платок
                </div>

                <div class="popover__close">
                    Закрыть
                    <div class="popover__close-icon">
                        <img src="../assets/images/icons/close.svg" alt="close-icon">
                    </div>
                </div>
            </div>

            <div class="popover__content">

                <slot name="popover__content_left">
                    <div class="product-slider">

                        <div class="product-slider__item product-slider__item_full-height">
                            <VueSlickCarousel :arrows="true" :fade="true" :infinite="true" :dots="true">
                                <slot name="slide-items">
                                    <div class="product-slider__img"><img src="../assets/images/popover-img.png"/></div>
                                </slot>
                            </VueSlickCarousel>
                        </div>

                    </div>
                </slot>

                <slot name="popover__content_right"></slot>

                <div class="btn-group">
                    <a href="#" class="btn-group__item btn-group__item_result btn-group__item_result-dark ">Выбрать
                        размер <span>M</span></a>
                </div>
            </div>

        </div>

        <span slot="reference">
            <slot name="popover__icon">
                <span class="btn-group__item_preview">
                    <img src="../assets/images/icons/eye.svg" alt="icon-eye">
                </span>
            </slot>
        </span>
    </popper>
</template>

<script>
    import VueSlickCarousel from 'vue-slick-carousel'
    import Popper from 'vue-popperjs';

    export default {
        name: "Popover",
        components: {
            VueSlickCarousel,
            'popper': Popper
        }
    }


</script>

<style lang="scss">
    @import "../assets/styles/components/popover";
</style>