<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <p class="h3 text-success fw-bold">Contact Manager
          <router-link to="/contacts/add" class="btn btn-success btn-sm"><i class="fa fa-plus-circle"></i> New</router-link>
        </p>
        <p class="fst-italic">Lorn lorn lorn lorn lorn lorn lorn lorn lorm lorn lorn lorn lorn lorn lorn lorn lorn lorm lorn lorn lorn lorn lorn lorn lorn lorn lorm lorn lorn lorn lorn lorn lorn lorn lorn lorm lorn lorn lorn lorn lorn lorn lorn lorn lorm lorn lorn lorn lorn lorn lprn </p>
        <form>
          <div class="row">
            <div class="col-md-6">
              <div class="row">
                <div class="col">
              <input type="text" class="form-control" placeholder="Search Name">
            </div>
            <div class="col">
              <input type="submit" class="btn btn-outline-dark">
            </div>
              </div>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
 
  <div class="container mt-3">
    <div class="row">
      <div class="col-md-6">
        <div class="card my-2 list-group-item-success shadow-lg">
          <div class="card-body">
            <div class="row align-items-center">
              <div class="col-sm-4">
                 <img src="https://imgs.search.brave.com/eg9ZWFBlvWt511V1bbSKOz-64P-j6X8f498x1uYpdxI/rs:fit:474:225:1/g:ce/aHR0cHM6Ly90c2Uy/Lm1tLmJpbmcubmV0/L3RoP2lkPU9JUC5L/Ny0zQUFqRlZxUnR2/RGw3SUJYWWhBSGFI/YSZwaWQ9QXBp" alt="" class="contact-img">
              </div>
              <div class="col-sm-7">
                <ul class="list-group">
                  <li class="list-group-item">Name: <span class="fw-bold">Name</span></li>
                  <li class="list-group-item">Email: <span class="fw-bold">Email@name.com</span></li>
                  <li class="list-group-item">Mobile: <span class="fw-bold">583639364</span></li>
                </ul>
              </div>
              <div class="col-sm-1 d-flex flex-column justify-content-center align-items-center">
                <router-link to="/contacts/view/:contactId" class="btn btn-warning my-1">
                  <i class="fa fa-eye"></i>
                </router-link>
                <router-link to="/contacts/edit/:contactId" class="btn btn-primary my-1">
                  <i class="fa fa-pen"></i>
                </router-link>
                <button class="btn btn-danger my-1">
                  <i class="fa fa-trash"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ContactService } from '@/services/ContactService';


export default {
    name:'ContantManager',
    data:function(){
      return{
        loading : false,
      contacts : [],
      errorMessage : null

      }
      
    },
    create : async function(){

      try {

        this.loading=true;
        let response = await ContactService.getAllContacts();
        this.contacts=response.data;
        this.loading=false;
        
      } catch (error) {
        this.errorMessage=error;
        this.loading=false;
        
      }
      
    },
    methods: {
      
    }

}
</script>

<style>

</style>