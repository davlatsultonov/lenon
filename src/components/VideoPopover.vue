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
                }" class="popover video-popover">

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

                <div class="video-block__item">
                    <slot>
                        <img src="../assets/images/upper-white.png" alt="" height="200">
                    </slot>

                    <div class="video-block__overlay"></div>
                </div>
            </div>

        </div>

        <span class="column-link__icon icon-play" slot="reference">
            <img src="../assets/images/icons/play.svg" alt="icon-play">
        </span>
    </popper>
</template>

<script>
    import Popper from 'vue-popperjs';

    export default {
        name: "Popover",
        components: {
            'popper': Popper
        }
    }


</script>

<style lang="scss">
    @import "../assets/styles/components/video-popover";
</style>