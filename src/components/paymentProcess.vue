<template>
   

   <link rel="stlysheet" href="style.css">
    <v-container>
        <v-divider
        ></v-divider>
        <v-row>
    <!-- <div class="card"></div>
        <v-container-title>
                <span class="text-h5">Documents</span>
            </v-container-title> -->


        <v-col cols="6" >
        <div d-flex >

            <v-checkbox
            class="ma-2 pa-2"
        v-model="certificationLetterForm"
        :label="'Certification (Letter Form)'"
        
        
    ></v-checkbox>
        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="certificationAuthentication"
        :label="'Certification Authentication'"
        ></v-checkbox>
        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="certificationGoodMoral"
        :label="'Certification Good Moral'"
        ></v-checkbox>

        <v-checkbox
        class="ma-2 pa-2"
        v-model="certificationOfCompletion"
        :label="'Certification of Completion'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="Diploma"
        :label="'Diploma'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="Ace"
        :label="'Ace Form'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="roForm"
        :label="'RO Form'"
        ></v-checkbox>

        
        <v-checkbox class="ma-2 pa-2"
        v-model="torNonEngineering"
        :label="'Transcript of Records (Non Engineering Graduate)'"
        >
      </v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="torEngineering"
        :label="'Transcript of Records (Engineering Graduates)'"
        ></v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="torPerPage"
        :label="'Transcript of Records per page (Non-Graduate, All Courses)'"
        ></v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="scannedPicture"
        :label="'Scanned Picture'"
        ></v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="certificateOfUnitsEarned"
        :label="'Certificate of Units Earned'"
        ></v-checkbox>    
        </div>        
        </v-col>
        <v-col cols="6" >
        <div d-flex >
            <v-checkbox
            class="ma-2 pa-2"
        v-model="certificationOfGraduation"
        :label="'Certification of Graduation'"
    ></v-checkbox>        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="honorableDismissal"
        :label="'Honorable Dismissal'"
        ></v-checkbox>
        
        <v-checkbox
        class="ma-2 pa-2"
        v-model="certificationOfNoId"
        :label="'Certification of No. ID'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="copyOfGrades"
        :label="`Copy of Grades Certificate of General Weighted Average (GWA)`"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="certificateOfNSTP"
        :label="'Certificate of NSTP Serial Number'"
        ></v-checkbox>

        <v-checkbox class="ma-2 pa-2"
        v-model="certificateOfSubjectDescription"
        :label="'Certificate of Subject Description'"
        ></v-checkbox>

        
        <v-checkbox class="ma-2 pa-2"
        v-model="certificateOfEnrollment"
        :label="'Certificate of Enrollment/No Tuition Fee'"
        >
      </v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="certificateOfRegistration"
        :label="'Certificate of Registration'"
        ></v-checkbox>
        <v-checkbox class="ma-2 pa-2"
        v-model="others"
        :label="'Others (Please Specify)'"
        ></v-checkbox>    
        </div>        
        </v-col>        
        </v-row>
        <v-row>
        <div>
            <v-btn
       
      color="purple-darken-2"
      
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
        <!-- <v-list-subheader>DOCUMENTS</v-list-subheader> -->
        
      </v-list-item></v-col>
          <v-col cols="2" > <v-list-item
        
         v-for="item in transactionChecked"
         :key="item.title"         
         :subtitle="'P '+ item.value"
        >
        <!-- <v-list-subheader>DOCUMENTS</v-list-subheader> -->
        
      </v-list-item></v-col>
        </v-row>
    
     
      
       
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
        sumProduct: 0,
        transactionChecked: [],
      }
    },
    watch:{
        },
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
          title: 'Others',
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
