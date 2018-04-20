<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Part 1 5 Points-->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <form action="">
                        <label for="firstName">First Name:<input id="firstName" title="firstName" type="text" v-model="userData.firstName"/></label><br>
                        <label for="lastName">Last Name:<input id="lastName" title="lastName" type="text" v-model="userData.lastName"/></label> <br>
                        <!-- Mail -->
                        <label for="email">Email:</label>
                        <input id="email" title="email" type="email" v-model="userData.Mail"> <br>
                        <!-- Password -->
                        <label for="password">Password:</label>
                        <input id="password" title="password" type="password" v-model="userData.Password"> <br>
                        Store Data:
                        <label for="storeYes">Yes<input id="storeYes" type="radio" value="true" v-model="userData.storeData"></label>
                        <label for="storeNo">No<input id="storeNo" type="radio" value="false" v-model="userData.storeData"></label>

                        <button type="button" @click.prevent="submitted">Submit</button>
                    </form>
                    <!-- Store Data? Yes/No -->

                    <!-- Part 2 5 Points -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Part 3 5 Points -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body" v-if="isSubmitted">
                        <p>Full Name: {{fullName}} </p>
                        <p>Mail: {{userData.Mail}}</p>
                        <p>Password: {{userData.Password}}</p>
                        <p>Store in Database?: {{userData.storeData}} </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: function ()
        {
            return {
                userData:
                {
                    firstName:'',
                    lastName:'',
                    Mail:'',
                    Password:'',
                    storeData: false
                },
                isSubmitted: false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true
            }
        },
        computed: {
            fullName: function () {
                return this.userData.firstName + ' ' + this.userData.lastName
            }
        }
    }
</script>

<style>
</style>
