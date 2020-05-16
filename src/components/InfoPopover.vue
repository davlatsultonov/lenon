<template>
    <popper trigger="hover"
            :options="{ placement: 'top' }" class="popover info-popover">

        <div class="popper">
            Доступно только с фасоном платья «Прямое» и «Трапеция»
        </div>

        <span class="info-popover__item" slot="reference">
            <img src="../assets/images/icons/question.svg" alt="question-icon">
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

<style lang="scss" >

</style>