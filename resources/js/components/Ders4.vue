<template>
  <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8 mt-5">
                <div class="card">
                    <div class="card-header">
                        Watch Proporties
                    </div>
                    <div class="card-body">
                        {{name}}
                        <div class="form-group">
                            <label for="">Ad Soyad</label>
                            <input type="text" class="form-control" v-model="name" 
                                v-bind:class="{'is-invalid':errors.length>0, 'is-valid':errors.length==0 && name!= ''}" />
                            <div class="invalid-feedback" >
                                <span :key="key" v-for="(error, key) in errors">{{error}}</span>
                            </div>
                        </div>

                        <button :disabled="errors.length > 0 || name==''" @click="create" class="btn btn-primary">Oluştur</button>
                    </div>
                </div>
                <user-list @deleteUser="deleteUsers" :users="users"></user-list>
            </div>
        </div>
    </div>
</template>

<script>

import userList from './userList.vue'

export default {

    components:{
        userList
    },
    data:()=>({
        name:'',
        errors:[],
        users:[],
    }),
    methods:{
        create(){
            this.users.push(this.name)
        },
        deleteUsers(key){
            this.$delete(this.users, key)
        }
    },
    watch:{
        name(val){
            this.errors= []
            if(val==''){
                this.errors.push('Ad soyad alanı boş bırakılamaz.')
                return;
            }
            if (val[0] !== val[0].toUpperCase()) {
                this.errors.push('Ad soyad alanın ilk harfi büyük olmalı.')
                return;
            }
            if (val.length<6 || val.length>25) {
                this.errors.push('Ad soyad alanı minimum 6 karakter, maksimum 25 karakter olmalıdır.')
                return;
            }
        }
    }
}
</script>

<style>

</style>