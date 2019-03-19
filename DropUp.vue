<template>
    <div class="dropup">
        <primary-button @click="clear()" class="dropbtn">
            {{ text }}
            <img class="img" src="/images/small-arrow.svg" />
        </primary-button>
        <div class="dropup-content">
            <div class="options" @click="clear">{{ buttonText }}</div>
            <div class="options" @click="select(option)" v-for="option in options">{{ option.name }}</div>
        </div>
    </div>
</template>

<script>
import PrimaryButton from 'components/Buttons/PrimaryButton';
export default {
    name: 'DropUp',
    props: ['options', 'buttonText'],
    data() {
        return {
            text: this.buttonText,
        };
    },
    methods: {
        select(option) {
            this.text = option.name;
            this.$emit('selected', option);
        },
        clear() {
            this.text = this.buttonText;
            this.$emit('clear');
        },
    },
    components: {
        PrimaryButton,
    },
};
</script>

<style scoped>
.dropbtn {
    color: white;
    padding: 1px;
    font-size: 11px;
    border: none;
    margin-right: 0.5rem;
}
.img {
    margin-left: 2rem;
}

.dropup {
    width: 5rem;
    height: 5rem;
    position: relative;
    display: inline-block;
}

.dropup-content {
    display: none;
    position: absolute;
    background-color: white;
    min-width: 160px;
    bottom: 5rem;
    z-index: 1;
    border-radius: 3px;
    box-shadow: 0 2px 9px 0 #00000080;
}
.options {
    padding: 1rem;
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
}

.options:hover {
    background-color: #e6eaf2;
}

.dropup:hover .dropup-content {
    display: block;
}
</style>
