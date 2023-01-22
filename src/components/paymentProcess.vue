<template>
   

   <link rel="stlysheet" href="style.css">
    <v-container>
        <v-divider
        ></v-divider>
        <v-row
      no-gutters
    >
    <div class="card"></div>
        <v-container-title>
                <span class="text-h5">Documents</span>
            </v-container-title>


        <v-col cols="" class="my-0">
        <div d-flex >

            <v-checkbox
            class="ma-2 pa-2"
        v-model="prod1"
        :label="'Product 1'"
    ></v-checkbox>
        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="prod2"
        :label="'Product 2'"
        ></v-checkbox>
        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="prod3"
        :label="'Product 3'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="prod4"
        :label="'Product 4'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="prod5"
        :label="'Product 5'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="prod6"
        :label="'Product 6'"
        ></v-checkbox>

        
        <v-checkbox class="ma-2 pa-2"
        v-model="prod7"
        :label="'Product 7'"
        ></v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="prod8"
        :label="'Product 8'"
        ></v-checkbox>
    
        </div>
        
        </v-col>
        </v-row>

        <v-row>
        <div>
            <v-btn
            v-model="submit"
            @click="submitButton()"
            variant="flat"
            position="right"
            
            >
            
        Submit Total
        </v-btn>
        </div>
        </v-row>
    



    
  </v-container>

  <v-container>

    <template>
    <v-row justify="center">
      <v-dialog
        v-model="resultDialog"
      >
        <template v-slot:activator="{ props }">
          <v-btn
            color="primary"
            v-bind="props"
          >
            Open Dialog
          </v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="text-h4">Transaction Preview</span>
            
          </v-card-title>

                <span class="text-h5">Documents</span>
      
          <v-card-text>
                {{ this.prod1 ? 'Product 1 ___________________________________ 20' : "" }}
          </v-card-text>

          <v-card-text>
                {{ this.prod2 ? 'Product 2 ___________________________________ 30' : "" }}
          </v-card-text>

          <v-card-text>
                {{ this.prod3 ? 'Product 3 ___________________________________ 40' : "" }}
          </v-card-text>

          <v-card-text>
                {{ this.prod4 ? 'Product 4 ___________________________________ 50' : "" }}
          </v-card-text>

          <v-card-text>
                {{ this.prod5 ? 'Product 5 ___________________________________ 50' : "" }}
          </v-card-text>

          <v-card-text>
                {{ this.prod6 ? 'Product 6 ___________________________________ 60' : "" }}
                
          </v-card-text>

              <v-card-text>
                 {{ 'Total Amount : ' + this.sumProduct }}
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="green-darken-1"
              variant="text"
              @click="resultDialog = false"
            >
              Cancel
            </v-btn>
            <v-btn
              color="green-darken-1"
              variant="text"
              @click="resultDialog = false"
            >
              Print
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </template>
  </v-container>
  </template>


  
  <script >
    //
    export default {
    computed: {
      
    },
    data () {
        
      return {
        submit:false,
        resultDialog:false,
        prod1: false,
        prod1Val: 0,
        prod2: false,
        prod2Val: 0,
        prod3: false,
        prod4: false,
        prod5: false,
        prod6: false,
        prod7: false,
        prod8: false,
        sumProduct: 0,
      }
    },
    watch:{
prod1(){
    if(this.prod1 == true){
           this.prod1Val= 20

        }else{
            this.prod1Val = 0
        }
},
prod2(){
    if(this.prod2 == true){
           this.prod2Val= 30

        }else{
            this.prod2Val = 0
        }
},
    },
    methods:{
    submitButton(){
        this.resultDialog = true;
        const sumProd =  this.prod1Val + this.prod2Val
        this.sumProduct = sumProd
        // console.log(sumProd)
    }
    },
  }



  
  </script>

  <style>

</style>
<!-- 
  <v-responsive class="d-flex align-center text-center fill-height">
    <v-img
      contain
      height="300"
      src="@/assets/logo.svg"
    />

    <div class="text-body-2 font-weight-light mb-n1">Welcome to</div>

    <h1 class="text-h2 font-weight-bold">Vuetify</h1>

    <div class="py-14" />

    <v-row class="d-flex align-center justify-center">
      <v-col cols="auto">
        <v-btn
          href="https://next.vuetifyjs.com/components/all/"
          min-width="164"
          rel="noopener noreferrer"
          target="_blank"
          variant="text"
        >
          <v-icon
            icon="mdi-view-dashboard"
            size="large"
            start
          />

          Components
        </v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn
          color="primary"
          href="https://next.vuetifyjs.com/introduction/why-vuetify/#feature-guides"
          min-width="228"
          rel="noopener noreferrer"
          size="x-large"
          target="_blank"
          variant="flat"
        >
          <v-icon
            icon="mdi-speedometer"
            size="large"
            start
          />

          Get Started
        </v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn
          href="https://community.vuetifyjs.com/"
          min-width="164"
          rel="noopener noreferrer"
          target="_blank"
          variant="text"
        >
          <v-icon
            icon="mdi-account-group"
            size="large"
            start
          />

          Community
        </v-btn>
      </v-col>
    </v-row>
  </v-responsive> -->