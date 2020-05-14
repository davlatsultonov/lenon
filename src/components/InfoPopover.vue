<template>
    <popper trigger="clickToToggle"
            :options="{
                  placement: 'top',
                  modifiers: {
                        name: 'offset',
                      options: {
                        offset: [0, -10],
                      }
                  }
                }" class="info-popover popover">

        <div class="popper">
            Доступно только с фасоном платья «Прямое» и «Трапеция»
        </div>

        <span slot="reference">
            <slot name="popover__icon">
                <span class="info-popover__item">
                    <img src="../assets/images/icons/question.svg" alt="question-icon">
                </span>
            </slot>
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
    .info-popover {
        position: relative;
        top: -4px;
        left: 2px;

        .popper {
            width: 135px;
            min-width: 135px;
            height: auto;
            padding: 10px 13px;
            font-size: 12px;
            line-height: 15px;
            text-align: left;
            left: -1px !important;
            top: -4px !important;
        }

        &__item {
            display: inline-block;
            width: 15px;
            height: 15px;
        }
    }

</style>