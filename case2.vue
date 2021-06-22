<template>
    <div class="some-counter">
        Count: {{ count }}
    </div>
</template>

<script>
export default {
    name: 'SomeCounter',

    data() {
        return {
            timer: null,
            count: 1
        };
    },

    created: () => {
        this.timer = setInterval(() => this.count++, 1000);
    },

    beforeDestroy: () => {
        clearInterval(this.timer);
    }
} 
</script>
