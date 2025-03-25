<template>
    <form autocomplete="off" @submit.prevent="submit" :ref="name" :event="event" :action="action" :method="method"
        class="needs-validation" novalidate>
        <slot></slot>
    </form>
</template>

<script>
export default {
    name: "FormTag",
    props: ["action", "method", "name", "event"],
    methods: {
        submit() {
            let myForm = this.$refs[this.$props.name];

            if (myForm.checkValidity()) {
                this.$emit(this.$props['event']);
            }
            myForm.classList.add('was-validated');
        }
    },
}
</script>