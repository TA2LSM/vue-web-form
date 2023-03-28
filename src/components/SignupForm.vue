<template>
    <!-- prevent default action of form and fire handleSubmit event -->
    <form @submit.prevent="handleSubmit">
        <label>E-mail:</label>
        <input type="email" required v-model="email">
        <!-- v-model directive will track input field and update email data immediately.
        This is a two way data binding. When this.email="" happens input field will also change -->

        <label>Password:</label>
        <input type="password" required v-model="password">

        <label style="margin-right: 15px;">Role:</label>
        <select v-model="role">
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
        </select>

        <!-- <div>
            <input type="checkbox" value="ta2lsm" v-model="names">
            <label>TA2LSM</label>
        </div>
        <div>
            <input type="checkbox" value="semih" v-model="names">
            <label>Semih</label>
        </div>
        <div>
            <input type="checkbox" value="batuhan" v-model="names">
            <label>Batuhan</label>
        </div> -->

        <label for="skill-input">Skills:</label>
        <input id="skill-input" type="text" v-model="tempSkill" @keyup="addSkill">
        <label for="skill-input">Press comma (,) to enter skill</label>
        <div v-for="skill in skills" :key="skill" class="pill">
            <span @click="deleteSkill(skill)">{{ skill }}</span>
        </div>

        <div class="terms">
            <input type="checkbox" required v-model="terms">
            <label>Accept terms and conditions</label>
        </div>

        <div class="submit">
            <button>Create an Account</button>
        </div>
    </form>

    <!-- v-model monitoring -->
    <div>
        <p>Email: <b>{{ email }}</b>, Password: <b>{{ password }}</b></p>
        <p>Role: <b>{{ role }}</b>, Terms Accepted: <b>{{ terms }}</b></p>
        <!-- <p>Names: <b>{{ names }}</b></p> -->
        <!-- <p>Skills: <b>{{ skills }}</b></p> -->
    </div>

</template>

<script>
    export default {
        name: 'SignupForm',
        // props: [''],

        data() {
            return {
                email: '',
                password: '',
                role: 'developer', // will be option's value (designer or developer)
                terms: false,
                // names: [],
                tempSkill: '',
                skills: [],
            }
        },

        // mounted() {
        //     this.email="semihsenol@gmail.com"
        //     // About v-model at template section this code will effect input's value
        // }

        methods: {
            addSkill(e) {
                // console.log(e);

                if(e.key === ',') {
                    this.tempSkill = this.tempSkill.replace(',', '');
                    // console.log(this.tempSkill);

                    if(!this.skills.includes(this.tempSkill) && this.tempSkill.length) {
                        this.skills.push(this.tempSkill);
                    }

                    this.tempSkill = '';
                }
            },
 
            deleteSkill(skill) {
                // "item" will stay in the array if it is not equal to "skill"
                this.skills = this.skills.filter(item => item !== skill);
            },

            handleSubmit() {
                console.log("form submitted");
            }
        }
    }
</script>

<style>
    form {
        max-width: 420px;
        margin: 30px auto;
        background: white;
        text-align: left;
        padding: 40px;
        border-radius: 10px;
    }

    label {
        color: #aaa;
        display: inline-block;
        margin: 25px 0 15px;
        font-size: 0.8rem;
        font-weight: bold;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    input, select {
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #ddd;
        color: #555;
        font-size: 1rem;
    }

    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
        /* top: 2px; */
    }

    .pill {
        display: inline-block;
        margin: 20px 10px 0 0;
        padding: 5px 10px;
        background: #eee;
        border-radius: 20px;
        font-size: 15px;
        letter-spacing: 1px;
        font-weight: bold;
        color: #777;
        cursor: pointer;
    }

    button {
        background: #0b6dff;
        border: 0;
        padding: 10px 20px;
        margin-top: 20px;
        color: white;
        border-radius: 20px;
        font-weight: bold;
    }

    .submit {
        text-align: center;
    }
</style>