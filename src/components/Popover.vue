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
    .popover {

     .popper {
            display: inline-block;
            box-sizing: border-box;
            min-width: 319px;
            height: 480px;
            box-shadow: 0 7px 19px -2px rgba(0, 0, 0, 0.23);
            background-color: white;
            border-radius: 5px;
            color: #000;
            padding: 50px 34px;
            left: 7px !important;
            top: -6px !important;
        }

        .product-slider {
            width: 251px;
            height: 375px;
        }

        &__header {
            position: relative;

            .option-block__title, .popover__close {
                position: absolute;
            }

            .option-block__title {
                top: -35px;
            }

            .popover__close {
                right: -22px;
                top: -38px;
                font-size: 12px;

                &-icon {
                    margin-left: 2px;
                    display: inline-block;
                    vertical-align: middle;
                }
            }
        }

        &_size {
            .popper {
                width: 550px;
                padding: 50px 28px;
            }

            .popover__content {

                .product-slider {
                    float: left;
                    margin-right: 20px;

                    &__item {

                        &_full-height {
                            .slick-prev {
                                left: 10px;
                            }

                            .slick-next {
                                right: 10px;
                            }
                        }
                    }

                }

                .product-style {
                    float: left;

                    &__item:not(:nth-child(5n)) {
                        margin-right: 0;
                    }

                    &__item:not(:nth-child(3n)) {
                        margin-right: 20px;
                    }

                    &__icon {
                        height: 44px;
                    }
                }
            }
        }
    }
</style>