<template>
    <popper trigger="clickToToggle"
            :options="{ placement: 'top' }" class="popover size-popover">

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
                                    <div class="product-slider__img"><img
                                            src="../assets/images/popover-img.png"/></div>
                                    <div class="product-slider__img"><img
                                            src="../assets/images/upper-part.png"/></div>
                                </slot>
                            </VueSlickCarousel>
                        </div>

                    </div>
                </slot>

                <slot name="popover__content_right">
                    <div class="product-style ">

                        <div class="product-style__item">
                            <button class="product-style__btn active">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">
                                <div class="product-style__checked"><span></span></div>
                            </button>

                            <div class="product-style__text">M</div>
                        </div>

                        <div class="product-style__item">
                            <button class="product-style__btn">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">

                                <div class="product-style__checked"><span></span></div>
                            </button>
                            <div class="product-style__text">S</div>
                        </div>

                        <div class="product-style__item">
                            <button class="product-style__btn">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">

                                <div class="product-style__checked"><span></span></div>
                            </button>
                            <div class="product-style__text">S</div>
                        </div>

                        <div class="product-style__item">
                            <button class="product-style__btn">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">
                                <div class="product-style__checked"><span></span></div>
                            </button>

                            <div class="product-style__text">M</div>
                        </div>

                        <div class="product-style__item">
                            <button class="product-style__btn">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">

                                <div class="product-style__checked"><span></span></div>
                            </button>
                            <div class="product-style__text">S</div>
                        </div>

                        <div class="product-style__item">
                            <button class="product-style__btn">
                                <img class="product-style__icon"
                                     src="../assets/images/icons/popover-size-img.png"
                                     alt="straight-icon">

                                <div class="product-style__checked"><span></span></div>
                            </button>
                            <div class="product-style__text">S</div>
                        </div>

                    </div>
                </slot>

                <div class="btn-group">
                    <a href="#" class="btn-group__item btn-group__item_result btn-group__item_result-dark ">Выбрать
                        размер <span>M</span></a>
                </div>
            </div>

        </div>

        <span class="column-link__icon icon-eye" slot="reference">
            <img src="../assets/images/icons/eye.svg" alt="icon-eye">
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

</style>