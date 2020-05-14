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
    @import "../assets/styles/components/info-popover";
</style>