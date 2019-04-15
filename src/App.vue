<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->
                    <FullName v-model="user.fullName"></FullName>
                    <div class="form-group">
                        <label for="email">email</label>
                        <input type="email" id="email" class="form-control" v-model="user.email">
                    </div>
                    <div class="form-group">
                        <label for="password">password</label>
                        <input type="password" id="password" class="form-control" v-model="user.password">
                    </div>
                    <div class="form-group">
                        <label>
                            <input type="radio" value="yes" v-model="saveData">yes
                        </label>
                        <label>
                            <input type="radio" value="no" v-model="saveData">no
                        </label>
                    </div>

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
            <div class="row">

                <!-- Exercise 2 -->
                <!-- Only display the Form if it has NOT been submitted -->
                <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button class="btn btn-primary" @click.prevent="isSubmited = !isSubmited">Submit</button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmited">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{user.fullName}}</p>
                        <p>Mail: {{user.email}}</p>
                        <p>Password: {{user.password}}</p>
                        <p>Store in Database?: {{saveData}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from "./FullName";
    export default {
        components: {FullName},
        data() {
            return {
                user: {
                    fullName:"Denis Larin",
                    email: "",
                    password: "",
                },
                isSubmited: false,
                saveData:"no"
            }
        }
    }
</script>

<style>
</style>
