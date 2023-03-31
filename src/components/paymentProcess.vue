<template>
    <v-container>
        <v-container class="ml-6" style="color: black; font-weight: bolder;">
          <v-row class="mt-10">

            <v-col cols="12" class="mt-10">
              <v-container class="mt-10">
                  <v-card height="800px">
                    <v-card-title style="background-color: lightgray; font-weight: bolder;"
                      class="py-3"
                      
                    >DOCUMENTS</v-card-title>
                    <v-row>
                      <v-col cols="3" class="text-no-wrap">
                        <v-checkbox
                      class="ma-2 pa-2"
                      v-model="certificationLetterForm"
                      :label="'Certification (Letter Form)'">
                    </v-checkbox>
                      </v-col>
                      <v-col cols="3" class="text-no-wrap">
                        <v-checkbox
                      class="ma-2 pa-2"
                      v-model="certificationAuthentication"
                      :label="'Certification Authentication'"
                      ></v-checkbox>
                      </v-col>
                      <v-col cols="3" class="text-no-wrap">
                      <v-checkbox
                      class="ma-2 pa-2"
                      v-model="certificationGoodMoral"
                      :label="'Certification Good Moral'"
                      ></v-checkbox>
                    </v-col>
                    <v-col cols="3" class="text-no-wrap">
                      <v-checkbox
                      class="ma-2 pa-2"
                      v-model="certificationOfCompletion"
                      :label="'Certification of Completion'"
                      ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                      v-model="Diploma"
                      :label="'Diploma'"
                      ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                      v-model="Ace"
                      :label="'Ace Form'"
                      ></v-checkbox>
                    </v-col>
                    <v-col cols="3" >
                      <v-checkbox class="ma-2 pa-2"
                      v-model="roForm"
                      :label="'RO Form'"
                      ></v-checkbox>  
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                        v-model="torNonEngineering"
                        :label="'Transcript of Records (Non Engineering Graduate)'"
                        >
                      </v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                        v-model="torEngineering"
                        :label="'Transcript of Records (Engineering Graduates)'"
                        ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                        v-model="torPerPage"
                        :label="'Transcript of Records per page (Non-Graduate, All Courses)'"
                        ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                        v-model="scannedPicture"
                        :label="'Scanned Picture'"
                        ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                        v-model="certificateOfUnitsEarned"
                        :label="'Certificate of Units Earned'"
                        ></v-checkbox>  
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox
                              class="ma-2 pa-2"
                          v-model="certificationOfGraduation"
                          :label="'Certification of Graduation'"
                      ></v-checkbox>  
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox
                    class="ma-2 pa-2"
                    v-model="honorableDismissal"
                    :label="'Honorable Dismissal'"
                    ></v-checkbox>  
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox
                    class="ma-2 pa-2"
                    v-model="certificationOfNoId"
                    :label="'Certification of No. ID'"
                    ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="copyOfGrades"
                    :label="`Copy of Grades Certificate of General Weighted Average (GWA)`"
                    ></v-checkbox>
                    </v-col>
                    <!-- <v-col cols="3">
                      
                    <v-checkbox class="ma-2 pa-2"
                    v-model="copyOfGrades"
                    :label="`Copy of Grades Certificate of General Weighted Average (GWA)`"
                    ></v-checkbox>
                    </v-col> -->
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="certificateOfNSTP"
                    :label="'Certificate of NSTP Serial Number'"
                    ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="certificateOfSubjectDescription"
                    :label="'Certificate of Subject Description'"
                    ></v-checkbox>

                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="certificateOfEnrollment"
                    :label="'Certificate of Enrollment/No Tuition Fee'"
                    >
                  </v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="certificateOfRegistration"
                    :label="'Certificate of Registration'"
                    ></v-checkbox>
                    </v-col>
                    <v-col cols="3">
                      <v-checkbox class="ma-2 pa-2"
                    v-model="others"
                    :label="'Others (Please Specify)'"
                    ></v-checkbox>  
                    </v-col>
                    <v-col cols="3">
                      <div>
                      <v-text-field 
                      v-model="othersSpecify"
                      clearable
                      v-if="this.others == true"
                      type="text" label="Please Specify" append
                      
                      required

                      ></v-text-field>
                      
                      </div>
                    </v-col>                  
                    </v-row>
                     </v-card>  
                  
                     
                </v-container>
            </v-col>
          </v-row>

<!-- ============================================= -->
      <!-- BUTTON FOR SUBMIT TRANSACTION -->

      

          <v-row>
              <v-col cols="4"></v-col>
             <v-col cols="4"> 
            </v-col>
            <v-col cols="4">

              <div>
            <v-btn
            style="color:white"
            size="large"
            width="100%"
            color="#8a0f24"      
            v-model="submit"          
            :disabled="submitDisabled"
            @click="submitButton()"
            variant="flat"
            position="right"            
            >            
            P R O C E E D
             </v-btn>
            </div>
            </v-col>

        </v-row>    
        </v-container>       
  </v-container>



  <!-- ============================================= -->
  <!-- THIS IS OPEN DIALOG CONTAINER - TRANSACTION -->
  <v-container>
    <template>
      <v-row justify="center">
    <v-dialog
      v-model="resultDialog"      
      width="1200"
      max-height="auto"
      :scrim="false"
      transition="dialog-bottom-transition"
    >
      <template v-slot:activator="{ props }">
        <v-btn
          color="primary"
          dark
          v-bind="props"
        >
          Open Dialog
        </v-btn>
      </template>
      <v-card>
        <v-toolbar
          dark
          color="gray"
        >
          <v-btn
            icon
            dark
            @click="closeTransaction()"
          >
            <v-icon>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title 
          style="font-weight: bolder;"      
          >Transaction Review</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
            <v-btn
          style="font-weight: bolder;"
              variant="text"
              @click="saveTransaction()"
            >
              Confirm Transaction
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <v-row>
          <v-col cols="">    <v-list-item
          style="font-weight: bolder;"
         v-for="item in transactionChecked"
         :key="item.title"
         :title="item.title"         
        >
      </v-list-item></v-col>
          <v-col cols="2" > <v-list-item
        
         v-for="item in transactionChecked"
         :key="item.title"         
         :subtitle="'P '+ item.value"
        >
      </v-list-item></v-col>
        </v-row>
      </v-card>
    </v-dialog>
  </v-row>
  </template>
  </v-container>

  </template>


  
  <script >
import { isHTMLTag } from '@vue/shared'

    //
    export default {
    computed: {
      
    },
    data :()=> {
      return {
    
        dialogLoading:false,
        resultDialog:false,
        certificationLetterFormVal:0,
        certificationLetterForm:false,
        certificationAuthentication:false,
        certificationAuthenticationVal:0,
        certificationGoodMoral: false,
        certificationGoodMoralVal:0,
        certificationOfCompletion:false,
        certificationOfCompletionVal:0,
        Diploma :false,
        DiplomaVal:0,
        Ace:false,
        AceVal:0,
        roForm:false,
        roFormVal:0,
        torNonEngineering:false,
        torNonEngineeringVal:0,
        torEngineering:false,
        torEngineeringVal:0,
        torPerPage:false,
        torPerPageVal:0,
        scannedPicture:false,
        scannedPictureVal:0,
        certificateOfUnitsEarned:false,
        certificateOfUnitsEarnedVal:0,
        certificationOfGraduation:false,
        certificationOfGraduationVal:0,
        honorableDismissal:false,
        honorableDismissalVal:0,
        certificationOfNoId:false,
        certificationOfNoIdVal:0,
        copyOfGrades:false,
        copyOfGradesVal:0,
        certificateOfNSTP:false,
        certificateOfNSTPVal:0,
        certificateOfSubjectDescription:false,
        certificateOfSubjectDescriptionVal:0,
        certificateOfEnrollment:false,
        certificateOfEnrollmentVal:0,
        certificateOfRegistration:false,
        certificateOfRegistrationVal:0,
        others:false,
        othersVal:0,
        submit:false,
        submitDisabled:false,
        sumProduct: 0,
        transactionChecked: [],
        othersSpecify: "Others",
      }
    },
    watch:{
    others(){
      this.othersSpecify = "Others"
      

        }
    },
    // othersSpecify(){
    //     if (this.othersSpecify) {
    //       this.submitDisabled = false          
    //     }else{
    //       this.submitDisabled = true          

    //     }
    // }
        // },
    methods:{
     submitButton(){

      if(this.certificationLetterForm == true){
           this.certificationLetterFormVal= 150
           this.transactionChecked.push({
          title: 'Certification (Letter Form)',
          value: 150,
        })
        }else{
            this.certificationLetterFormVal = 0
        }

        if(this.certificationAuthentication == true){
           this.certificationAuthenticationVal= 150
           this.transactionChecked.push({
          title: 'Certification Authentication',
          value: 150,
        })
        }else{
            this.certificationAuthenticationVal = 0
        }

        if(this.certificationGoodMoral == true){
           this.certificationGoodMoralVal= 150
           this.transactionChecked.push({
          title: 'Certification Good Moral',
          value: 150,
        })
        }else{
            this.certificationGoodMoralVal = 0
        }

        if(this.certificationOfCompletion == true){
           this.certificationOfCompletionVal= 150
           this.transactionChecked.push({
          title: 'Certification of Completion',
          value: 150,
        }) 
        }else{
            this.certificationOfCompletionVal = 0
        }

        if(this.Diploma == true){
           this.DiplomaVal= 200
           this.transactionChecked.push({
          title: 'Diploma',
          value: 200,
        }) 
        }else{
            this.DiplomaVal = 0
        }

        if(this.Ace == true){
           this.AceVal= 0
           this.transactionChecked.push({
          title: 'Ace Form',
          value: 0,
        }) 
        }else{
            this.AceVal = 0
        }


        if(this.roForm == true){
           this.roFormVal= 0
           this.transactionChecked.push({
          title: 'RO Form',
          value: 0,
        }) 
        }else{
            this.roFormVal = 0
        }


        if(this.torNonEngineering == true){
           this.torNonEngineeringVal= 350
           this.transactionChecked.push({
          title: 'Transcript of Records (Non Engineering Graduate)',
          value: 350,
        }) 
        }else{
            this.torNonEngineeringVal = 0
        }

        if(this.torEngineering == true){
           this.torEngineeringVal= 450
           this.transactionChecked.push({
          title: 'Transcript of Records (Engineering Graduates)',
          value: 450,
        }) 
        }else{
            this.torEngineeringVal = 0
        }


        if(this.torPerPage == true){
           this.torPerPageVal= 100
           this.transactionChecked.push({
          title: 'Transcript of Records per page (Non-Graduate, All Courses)',
          value: 100,
        }) 
        }else{
            this.torPerPageVal = 0
        }


        if(this.scannedPicture == true){
           this.scannedPictureVal= 50
           this.transactionChecked.push({
          title: 'Scanned Picture',
          value: 50,
        }) 
        }else{
            this.scannedPictureVal = 0
        }

        if(this.certificateOfUnitsEarned == true){
           this.certificateOfUnitsEarnedVal= 0
           this.transactionChecked.push({
          title: 'Certificate of Units Earned',
          value: 0,
        }) 
        }else{
            this.certificateOfUnitsEarnedVal = 0
        }


        if(this.certificationOfGraduation == true){
           this.certificationOfGraduationVal= 600
           this.transactionChecked.push({
          title: 'Certification of Graduation',
          value: 600,
        }) 
        }else{
            this.certificationOfGraduationVal = 0
        }

        if(this.honorableDismissal == true){
           this.honorableDismissalVal= 0
           this.transactionChecked.push({
          title: 'Honorable Dismissal',
          value: 0,
        }) 
        }else{
            this.honorableDismissalVal = 0
        }

        if(this.certificationOfNoId == true){
           this.certificationOfNoIdVal= 0
           this.transactionChecked.push({
          title: 'Certification of No. ID',
          value: 0,
        }) 
        }else{
            this.certificationOfNoIdVal = 0
        }

        if(this.copyOfGrades == true){
           this.copyOfGradesVal= 0
           this.transactionChecked.push({
          title: 'Copy of Grades Certificate of General Weighted Average (GWA)',
          value: 0,
        }) 
        }else{
            this.copyOfGradesVal = 0
        }

        if(this.certificateOfNSTP == true){
           this.certificateOfNSTPVal= 0
           this.transactionChecked.push({
          title: 'Certificate of NSTP Serial Number',
          value: 0,
        }) 
        }else{
            this.certificateOfNSTPVal = 0
        }

        if(this.certificateOfSubjectDescription == true){
           this.certificateOfSubjectDescriptionVal= 0
           this.transactionChecked.push({
          title: 'CCertificate of Subject Description',
          value: 0,
        }) 
        }else{
            this.certificateOfSubjectDescriptionVal = 0
        }

        if(this.certificateOfEnrollment == true){
           this.certificateOfEnrollmentVal= 0
           this.transactionChecked.push({
          title: 'Certificate of Enrollment/No Tuition Fee',
          value: 0,
        }) 
        }else{
            this.certificateOfEnrollmentVal = 0
        }

        if(this.certificateOfRegistration == true){
           this.certificateOfRegistrationVal= 0
           this.transactionChecked.push({
          title: 'Certificate of Registration',
          value: 0,
        }) 
        }else{
            this.certificateOfRegistrationVal = 0
        }

        if(this.others == true){
           this.othersVal= 0
           this.transactionChecked.push({
          title: this.othersSpecify,
          value: 0,
        }) 
        }else{
            this.othersVal = 0
        }
      
        this.resultDialog = true;
        const sumVal = this.transactionChecked
        let finalSum = 0;
        
        
         for (let i = 0; i < sumVal.length; i++) {
           const newItem = sumVal[i].value;
          finalSum += newItem
          
         }
        
        // console.log(finalSum)

        this.transactionChecked.push({
          title: 'TOTAL AMOUNT',
          value: finalSum,
        }) 
    },
    saveTransaction(){
      this.resultDialog = false
      this.certificationLetterForm = false
      this.certificationAuthentication= false
      this.certificationGoodMoral= false
      this.Ace= false
      this.others= false
      this.scannedPicture= false
      this.honorableDismissal= false
      this.certificateOfUnitsEarned= false
      this.certificateOfRegistration= false
      this.certificateOfEnrollment= false
      this.certificationOfNoId= false
      this.certificateOfSubjectDescription= false
      this.certificateOfNSTP= false
      this.certificationOfGraduation= false
      this.copyOfGrades= false
      this.torEngineering= false
      this.torPerPage= false
      this.torNonEngineering= false
      this.roForm= false
      this.Diploma= false
      this.othersSpecify=null
      this.certificationOfCompletion= false
      this.transactionChecked= []
    },
    closeTransaction(){
      this.resultDialog = false
      this.certificationLetterForm = false
      this.certificationAuthentication= false
      this.certificationGoodMoral= false
      this.Ace= false
      this.others= false
      this.scannedPicture= false
      this.honorableDismissal= false
      this.certificateOfUnitsEarned= false
      this.certificateOfRegistration= false
      this.certificateOfEnrollment= false
      this.certificationOfNoId= false
      this.certificateOfSubjectDescription= false
      this.certificateOfNSTP= false
      this.certificationOfGraduation= false
      this.copyOfGrades= false
      this.torEngineering= false
      this.torPerPage= false
      this.torNonEngineering= false
      this.roForm= false
      this.Diploma= false
      this.othersSpecify=null
      this.certificationOfCompletion= false
      this.transactionChecked= []
    },
    },
  }



  
  </script>

  <style>
.custom-transform-class
    {text-transform: uppercase}


    .dialog-bottom-transition-enter-active,
.dialog-bottom-transition-leave-active {
  transition: transform .2s ease-in-out;
}
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
