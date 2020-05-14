<template>
    <popper trigger="clickToToggle"
            @show="show"
            :options="{ placement: 'top' }" class="popover video-popover">

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

                <div class="video-popover__item">
                    <slot>
                        <img src="../assets/images/video-bg.png" alt="" height="200">
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

        <div class="column-link" style="right: -2px;" slot="reference">
            <a href="#" @click.prevent>
                Смотреть
            </a>

            <span class="column-link__icon icon-play" >
                <img src="../assets/images/icons/play.svg" alt="icon-play">
            </span>

        </div>
    </popper>
</template>

<script>
    import Popper from 'vue-popperjs';

    export default {
        name: "Popover",
        components: {
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