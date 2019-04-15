<template>
    <div>
        <div class="form-group">
            <label for="FirstName">First Name</label>
            <input type="text" id="FirstName" class="form-control" :value="firstName" @input="nameChange(true, $event)">
        </div>
        <div class="form-group">
            <label for="LastName">Last Name</label>
            <input type="text" id="LastName" class="form-control" :value="lastName" @input="nameChange(false, $event)">
        </div>
    </div>
</template>

<script>
    export default {
        name: "FullName",
        props:['value'],
        methods:{
            nameChange(isName, event){
                let name = "";
                if (isName){
                    name = event.target.value + " " + this.lastName;
                }
                else{
                    name = this.firstName + " " + event.target.value;
                }
                this.$emit('input',name);
            }
        },
        computed:{
            firstName(){
                return this.$props.value.split(" ")[0];
            },
            lastName(){
                return this.$props.value.split(" ")[1];
            }
        }
    }
</script>

<style scoped>

</style>