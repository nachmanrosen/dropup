<template>
    <div class="dropup">
        <div class="dropbtn">
            {{ text }}
        </div>
        <div class="dropup-content">
            <div class="options" @click="clear">Clear</div>
            <div class="options" v-for="option in options"  @click="select(option)">
                <span> {{ option.name }}</span>
                <span v-if="option.price">{{option.price}}</span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'DropUp',
        props: ['options', 'multiSelect'],
        data() {
            return {
                text: '',
                selected: [],
            };
        },
        methods: {
            select(item) {
                this.selected.push(item);
                !this.multiSelect ?  this.selected.filter(item == item) :'';
                this.$emit('select', this.selected);
                this.text = this.selected.map(i =>i.name).toString();
            },
            clear() {
                this.text = '';
                this.selected = {};
            },
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
