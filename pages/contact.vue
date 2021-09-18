<template>
    <v-container>
        <h1>Contact Us</h1>
        <v-form ref="contactForm" v-model="valid" @submit.prevent="submit">
            <fieldset>
                <legend>Contact Information <v-icon>mdi-account-outline</v-icon></legend>
                <v-row>
                    <v-col cols="12" sm="6" xl="3">

                        <v-text-field
                            v-model="firstName"
                            label="First Name"
                            :rules="requiredRules"
                        ></v-text-field>
                    </v-col>
                    <v-col cols="12" sm="6" xl="3">
                        <v-text-field
                            v-model="lastName"
                            label="Last Name"
                            :rules="requiredRules"
                        ></v-text-field>
                    </v-col>
                    <v-col cols="12" md="8" lg="6">
                        <VuePhoneNumberInput v-model="phone" :only-countries="['US']" />
                        <!-- <v-text-field
                            v-model="phone"
                            label="Phone"
                            type="tel"
                            :rules="phoneRules"
                            prepend-icon="mdi-phone-outline"
                        ></v-text-field> -->
                    </v-col>
                    <v-col cols="12" md="8" lg="6">
                        <v-text-field
                            v-model="email"
                            label="E-mail"
                            type="email"
                            :rules="emailRules"
                            prepend-icon="mdi-email-outline"
                        ></v-text-field>
                    </v-col>
                </v-row>
            </fieldset>
            <fieldset>
                <legend>Email Content <v-icon>mdi-text-long</v-icon></legend>
                <v-row>
                    <v-col cols="12" lg="8">
                        <v-text-field
                            v-model="subject"
                            label="Subject"
                            :rules="requiredRules"
                        ></v-text-field>
                    </v-col>
                    <v-col cols="12">
                        <v-textarea
                            v-model="content"
                            outlined
                            auto-grow
                            label="Content"
                            :rules="requiredRules"
                        ></v-textarea>
                    </v-col>
                </v-row>
            </fieldset>
            <v-btn type="submit" :disabled="!valid" color="success">Submit</v-btn>
        </v-form>
        <v-alert
            :value="alert"
            dismissible
            color="green"
            dark
            border="top"
            icon="mdi-home"
            transition="scale-transition"
        >
            Thank you for contacting HoneyDo. We'll be in touch using email address or phone number you provided.
            You'll be redirected back to our home page shortly.
        </v-alert>
    </v-container>
</template>

<script>
import emailjs from 'emailjs-com';
import VuePhoneNumberInput from 'vue-phone-number-input';
import 'vue-phone-number-input/dist/vue-phone-number-input.css';
 
// Vue.component('vue-phone-number-input', VuePhoneNumberInput);
    export default {
        components: {
            VuePhoneNumberInput,
        },
        data() {
            return {
                alert: false,
                valid: false,
                firstName: null,
                lastName: null,
                phone: null,
                email: null,
                subject: null,
                content: null,
                emailRules: [
                    v => !!v || 'E-mail is required',
                    v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
                ],
                phoneRules: [
                    v => !!v || 'E-mail is required',
                    v => /^\d{10}$/.test(v) || 'Phone number must be valid'
                ],
                requiredRules: [
                    v => !!v || 'Name is required',
                ]
            }
        },
        computed: {
            fullName() {
                return this.firstName + ' ' + this.lastName 
            }
        },
        methods: {
            submit() {
                const userID = "user_cfv28p3w2JNzUHzRiXW1l"
                const templateID = "template_m2iq1ad"
                const serviceID = "service_r9zmqdt"
                const templateParams = {
                    reply_to: this.email,
                    message: this.content,
                    from_name: this.fullName,
                    phone: this.phone,
                }
                emailjs.send(serviceID, templateID, templateParams, userID)
                this.$refs.contactForm.reset();
                this.alert=true
                setTimeout(function () {
                    this.$nuxt.$router.push('/') // will redirect to home page
                }, 3000); // will call the function after 3 secs.
            }
        },
    }
</script>

<style lang="scss" scoped>
fieldset {
    padding: 1em;
    margin-top: 15px;
    margin-bottom: 15px;
}
</style>