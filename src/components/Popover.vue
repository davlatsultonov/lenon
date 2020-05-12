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
                }">

        <div class="popper popover">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deleniti, est incidunt ipsum iusto maxime
            obcaecati pariatur quibusdam quisquam repellendus soluta!

        </div>

        <span class="btn-group__item-preview" slot="reference">
            <img src="../assets/images/icons/eye.svg" alt="icon-eye">
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

<style scoped >
    .popper.popover {
        display: inline-block;
        box-sizing: border-box;
        width: 319px;
        height: 480px;
        box-shadow: 0 7px 19px -2px rgba(0, 0, 0, 0.23);
        background-color: white;
        border-radius: 5px;
        color: #000;
        padding: 50px 34px;
        left: 7px !important;
        top: -6px!important;
    }
</style>