<template>
  <v-container fluid>
    <v-row>
      <v-col cols="6" md="6">
        <v-card
          class="mx-auto pa-4 rounded-xl rounded-be-xl"
          max-width="1000"
          max-height="600"
          shaped
          raised
        >
          <v-card-title> Documents </v-card-title>

          <v-card-text>
            <v-row class="text-center" style="margin: 0">
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 1'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 2'"
                ></v-checkbox>
              </v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 3'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 4'"
                ></v-checkbox>
              </v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 5'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 6'"
                ></v-checkbox>
              </v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 7'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 8'"
                ></v-checkbox>
              </v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 9'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 10'"
                ></v-checkbox>
              </v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod1"
                  :label="'Product 11'"
                ></v-checkbox
              ></v-col>
              <v-col cols="6">
                <v-checkbox
                  class="text-no-wrap"
                  v-model="prod2"
                  :label="'Product 12'"
                ></v-checkbox>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>

      <v-col cols="6" md="6">
        <v-row>
          <v-col cols="12">
            <v-card
              class="mx-auto pa-4 rounded-xl rounded-be-xl"
              max-width="700"
              max-height="400"
              shaped
              raised
            >
              <v-card-title> User Information</v-card-title>

              <v-card-text>
                <v-container fluid>
                  <v-row class="text-center">
                    <v-col cols="12">
                      <span>aoshdoasjdoajosdjasdjjp</span>
                    </v-col>
                    <v-col cols="12">
                      <span>aoshdoasjdoajosdjasdjjp</span>
                    </v-col>
                    <v-col cols="12">
                      <span>aoshdoasjdoajosdjasdjjp</span>
                    </v-col>
                    <v-col cols="12">
                      <span>aoshdoasjdoajosdjasdjjp</span>
                    </v-col>
                  </v-row>
                </v-container>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="4"></v-col>
          <v-col cols="4">
            <v-btn
              block
              class="mb-4 rounded-xl rounded-be-xl"
              color="white"
              size="x-large"
              variant="flat"
              @click="loading = !loading"
            >
              C A N C E L
            </v-btn>
          </v-col>
          <v-col cols="4">
            <v-btn
              block
              class="mb-4 rounded-xl rounded-be-xl"
              color="red"
              size="x-large"
              variant="flat"
              @click="loading = !loading"
            >
              P R O C E E D
            </v-btn>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  computed: {},
  data() {
    return {
      submit: false,
      resultDialog: false,
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
      documentList: [
        { text: "Product 1", value: 120 },
        { text: "Product 2", value: 120 },
        { text: "Product 3", value: 120 },
        { text: "Product 4", value: 120 },
        { text: "Product 5", value: 120 },
      ],
    };
  },
  watch: {
    prod1() {
      if (this.prod1 == true) {
        this.prod1Val = 20;
      } else {
        this.prod1Val = 0;
      }
    },
    prod2() {
      if (this.prod2 == true) {
        this.prod2Val = 30;
      } else {
        this.prod2Val = 0;
      }
    },
  },
  methods: {
    submitButton() {
      this.resultDialog = false;

      const sumProd = this.prod1Val + this.prod3Val;

      this.sumProduct = sumProd;
      this.sumProductsOne = sumProd;
      console.log(sumProd);
    },
  },
};
</script>
