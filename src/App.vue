<template>
    <div class="container">
        <form v-if="!submited">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <div class="panel panel-default">
                        <div class="panel-heading">
                            <h4>Sign up</h4>
                        </div>
                        <div class="panel-body">
                            <app-name 
                                v-model="name"
                            ></app-name>
                            <div class="row" style="margin:5px">
                                <input 
                                    type="email"                             
                                    v-model.trim="mail">
                            </div>
                            <div class="row" style="margin:5px">
                                <input 
                                    type="password"
                                    v-model.lazy="password">
                            </div>    
                        </div>
                        <div class="form-check" style="margin-left:25px">
                            <input 
                                type="checkbox" 
                                class="form-check-input" 
                                id="checkOut" 
                                v-model="store" 
                            >
                            <label 
                                class="form-check-label" 
                                for="exampleCheck1"                           
                            >Store Data</label>
                        </div>
                    <button 
                        type="submit" 
                        class="btn btn-primary" 
                        style="margin:15px"
                        @click.prevent="submit"
                    >Submit</button>                         
                    </div>            
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submited">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ name }}</p>
                        <p>Mail: {{ mail }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ store }} </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import fullName from './fullName.vue';
    export default {
        data() {
            return {
                name: 'Gonzalo Alvarez',
                mail: '@',
                password: '',
                store: false,
                submited: false
            };            
        },
        methods: {
            submit() {
                alert('asd');
                this.submited=true;
            }
        },
        components: {
            'app-name': fullName
        }
    }
</script>

<style>
</style>
