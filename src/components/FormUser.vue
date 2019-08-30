<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
    
                    <div class="card-body">
                        <form @submit="formSubmit">
                        <strong>Firstname:</strong>
                        <input type="text" class="form-control" v-model="firstname">
                        <strong>Middlename:</strong>
                        <input type="text" class="form-control" v-model="middlename">
                        <strong>Lastname:</strong>
                        <input type="text" class="form-control" v-model="lastname">
                        <strong>Cityid:</strong>
                        <input type="number" class="form-control" v-model="cityid">
                        <strong>District:</strong>
                        <input type="text" class="form-control" v-model="district">
                        <strong>Stateid:</strong>
                        <input type="number" class="form-control" v-model="stateid">
                        <strong>Zip:</strong>
                        <input type="text" class="form-control" v-model="zip">
                        <strong>Country:</strong>
                        <input type="text" class="form-control" v-model="country">
                        <strong>Phone:</strong>
                        <input type="text" class="form-control" v-model="phone">
                        <strong>Email:</strong>
                        <input type="text" class="form-control" v-model="email">
                        <strong>Notes:</strong>
                        <input type="text" class="form-control" v-model="notes">
                        
                        <button class="btn btn-success">Submit</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
     
<script>
import axios from 'axios';

    export default {
        data() {
            return {
              firstname: '',
              middlename: '',
              lastname: '',
              cityid: 1,
              district: '',
              stateid: 1,
              zip: '',
              country: '',
              phone: '',
              email: '',
              notes: '',
              status: true
            };
        },
        methods: {
            formSubmit(e) {
                e.preventDefault();
                    axios.post('http://localhost:3000/user', {
                    firstname: this.firstname,
                    middlename: this.middlename,
                    lastname: this.lastname,
                    cityid: this.cityid,
                    district: this.district,
                    stateid: this.stateid,
                    zip: this.zip,
                    country: this.country,
                    phone: this.phone,
                    email: this.email,
                    notes: this.notes,
                    status: this.status
                })
            }
        }
    }
</script>