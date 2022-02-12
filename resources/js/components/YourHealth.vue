<template>
    <div class="main-container">
        <hero-component></hero-component>
        <div class="test">
            <h2>What is your need?</h2>
            <div class="main-feature">
                <div class="main-feature-container">
                    <div class="add-doctor">
                        <p>{{ form_heading }}

                            <svg v-if="is_Active_Patient || is_Active_Doctor" xmlns="http://www.w3.org/2000/svg" width="33" height="33" fill="currentColor" class="bi bi-arrow-right" viewBox="0 0 16 16">
                                <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>
                            </svg>

                            <svg v-else xmlns="http://www.w3.org/2000/svg" width="33" height="33" fill="currentColor" class="bi bi-arrow-down" viewBox="0 0 16 16">
                                <path fill-rule="evenodd" d="M8 1a.5.5 0 0 1 .5.5v11.793l3.146-3.147a.5.5 0 0 1 .708.708l-4 4a.5.5 0 0 1-.708 0l-4-4a.5.5 0 0 1 .708-.708L7.5 13.293V1.5A.5.5 0 0 1 8 1z"/>
                            </svg>
                        </p>
                        <p>Make your health data usable</p>
                        <p>Make your biomedical data easily accessible and securely usable in your environment.
                            Accelerate breakthroughs and cure diseases.</p>
                        <div class="d-flex justify-content-between">
                            <Button @clicked="openDoctorFormContainer"
                                    text="Doctor Form"
                                    @click="showMobileMenu = !showMobileMenu"
                                    :class="{ active: is_Active_Doctor}"
                            ></Button>
                            <Button @clicked="openPatientFormContainer"
                                    :class="{ active: is_Active_Patient}"
                                    text="Patient Form"></Button>
                        </div>

                    </div>

                    <div v-if="this.open_doctor_form_container" class="complete-form">
                    <text-input
                        label="First name"
                        varient="text"
                        name="first_name"
                        :value="formState.doctor_data.first_name"
                        class="first-name-input"
                        placeholder="First Name"
                        @typing="(v)=> {
                            formState.doctor_data.first_name = v
                        }"
                    ></text-input>
                        <p>{{formState.doctor_data.first_name}}</p>

                        <text-input
                            label="Last name"
                            varient="text"
                            name="last_name"
                            :value="formState.doctor_data.last_name"
                            class="last-name-input"
                            placeholder="Last Name"
                            @typing="(v)=> {
                            formState.doctor_data.last_name = v
                        }"
                        ></text-input>
                        <p>{{formState.doctor_data.last_name}}</p>

                        <text-input
                            label="Email"
                            varient="email"
                            name="email"
                            :value="formState.doctor_data.email"
                            class="email-input"
                            placeholder="Email"
                            @typing="(v)=> {
                            formState.doctor_data.email = v
                        }"
                        ></text-input>
                        <p>{{formState.doctor_data.email}}</p>

                        <text-input
                            label="Main qualification"
                            varient="text"
                            name="main-qualification"
                            :value="formState.doctor_data.main_qualification"
                            class="main-qualification-input"
                            placeholder="Main qualification"
                            @typing="(v)=> {
                            formState.doctor_data.main_qualification = v
                        }"
                        ></text-input>
                        <p>{{formState.doctor_data.main_qualification}}</p>
                    </div>


<!--                    PATIENT FORM-->

                    <div v-if="this.open_patient_form_container" class="complete-form patient-form">
                        <text-input
                            label="First name"
                            varient="text"
                            name="first_name"
                            :value="formState.patient_data.first_name"
                            class="first-name-input"
                            placeholder="First Name"
                            @typing="(v)=> {
                            formState.patient_data.first_name = v
                        }"
                        ></text-input>
                        <p>{{formState.patient_data.first_name}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
    import Navigation from "./nav-components/Navigation";
    import HeroComponent from "./HeroComponent";
    import TextInput from "./FormElements/TextInput";
    import Button from "./Button/Button";

    export default {
        components: {Button, TextInput, HeroComponent, Navigation},

        data() {
            return {
                formState: {
                    doctor_data: {
                        first_name: '',
                        last_name: '',
                        email: '',
                        main_qualification: '',
                    },

                    patient_data: {
                        first_name: '',
                        last_name: '',
                        email: '',
                    },
                },
                open_doctor_form_container: false,
                open_patient_form_container: false,
                is_Active_Doctor: false,
                is_Active_Patient: false,
                form_heading: 'SELECT A FORM'
            };
        },

        methods: {
            openDoctorFormContainer() {
                this.open_doctor_form_container = true;
                this.open_patient_form_container = false;
                this.is_Active_Doctor = true;
                this.is_Active_Patient = false;
                this.form_heading = 'You are completing: DOCTOR FORM';
            },

            openPatientFormContainer() {
                this.open_patient_form_container = true;
                this.open_doctor_form_container = false;
                this.is_Active_Patient = true;
                this.is_Active_Doctor = false;
                this.form_heading = 'You are completing: PATIENT FORM';
            }
        }
    }
</script>

<style scoped lang="scss">

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

.main-container {
    .test {
        h2 {
            color: #FFFFFF;
            background-color: #171A1E;
            font-family: "Poppins", Sans-serif;
            font-size: 3.5em;
            font-weight: 600;
            padding: 80px 0 0 100px;
        }
    }
    .main-feature {
        width: 100%;
        height: 100vh;
        background-color: #171A1E;
        justify-content: center;
        display: flex;

        .main-feature-container {
            width: 1350px;
            display: flex;
            justify-content: space-around;
            align-items: center;
            text-align: center  ;

            .add-doctor {
                background-color: transparent;
                background-image: linear-gradient(45deg, #2FDFBB 0%, #2295AE 65%);
                border-radius: 25px;
                width: 600px;
                height: 690px;
                text-align: start;
                padding: 60px 60px 60px 60px;

                p:first-of-type  {
                    color: white;
                    font-family: "Inter", Sans-serif;
                    font-size: 1.2rem;
                    font-weight: 600;
                }
                p:nth-child(2) {
                    color: white;
                    font-family: "Poppins", Sans-serif;
                    font-size: 60px;
                    font-weight: 500;
                    line-height: 1em;
                    padding: 45px 0;
                }
                p:nth-child(3) {
                    text-align: left;
                    color: white;
                    font-family: "Inter", Sans-serif;
                    font-size: 25px;
                    font-weight: 500;
                    line-height: 1.5em;
                }

                button {
                    border: none;
                    font-family: "Inter", Sans-serif;
                    font-size: 15px;
                    font-weight: 600;
                    fill: #FFFFFF;
                    color: #FFFFFF;
                    background-color: #2C72DB;
                    border-radius: 72px 72px 72px 72px;
                    padding: 17px 45px 17px 45px;
                    margin-top: 50px;
                }
            }

            .complete-form {
                background-color: transparent;
                background-image: linear-gradient(210deg, #2C72DB 0%, #A389AF 68%);
                border-radius: 25px;
                width: 610px;
                height: 690px;
            }
        }
    }
    .patient-form {
        background-image: linear-gradient(210deg, #A389AF 0%, #346abb 48%  ) !important;
    }
    .active {
        background-color: black  !important;
        pointer-events: none;
    }
}
</style>

