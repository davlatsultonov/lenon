<template>
    <popper trigger="clickToToggle"
            :options="{ placement: 'top' }" class="popover video-popover">

        <div class="popper">

            <div class="popover__header">
                <div class="option-block__title">
                    Видео-инструкция
                </div>

                <div class="popover__close">
                    Закрыть
                    <div class="popover__close-icon">
                        <img src="../assets/images/icons/close.svg" alt="close-icon">
                    </div>
                </div>
            </div>

            <div class="popover__content">

                <div class="video-popover__item">
                    <slot>
                        <iframe
                                src="">
                        </iframe>
                    </slot>

                    <div class="video-items">
                        <a href="#" class="" class="video-items__btn">
                            <img src="../assets/images/icons/video-play-icon.svg" alt="video-play-icon">
                            <span>
                                Смотреть
                            </span>
                        </a>


                        <div class="video-items__quality">
                            HD720, 25Mb
                        </div>
                    </div>

                    <div class="video-popover__overlay"></div>
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

</style>