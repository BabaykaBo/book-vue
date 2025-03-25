<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <h3>Login</h3>
                <form-tag name="myform" event="myevent" @myevent="submitHandler">
                    <text-input v-model="email" required="true" label="Email" name="email" type="email"></text-input>
                    <text-input v-model="password" required="true" label="Password" name="password"
                        type="password"></text-input>
                    <hr>
                    <input type="submit" value="Login" class="btn btn-primary">
                </form-tag>
            </div>
        </div>
    </div>
</template>

<script>
import TextInput from "./../components/forms/TextInput.vue"
import FormTag from "./../components/forms/FormTag.vue"

export default {
    name: "LoginComponent",
    components: {
        'text-input': TextInput,
        'form-tag': FormTag,
    },
    data() {
        return {
            "email": "",
            "password": "",
        }
    },
    methods: {
        submitHandler() {
            console.log('Success');
        }
    },
}
</script>