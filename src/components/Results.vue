<template>
  <v-sheet max-width="max-content" class="pt-0">
    <v-container>
      <v-row>
        <v-col cols="12" md="2" sm="12">
          <v-img 
            src="../assets/defaqto-expert-rated.png"
            width="150"
            alt="defaqto 5 star home insurance"
          ></v-img>
        </v-col>
        <v-col cols="12" md="7" sm="12" xs="12">
          <h1>Your home insurance quotes <br> for Jen Pomfret</h1>
        </v-col>
        <v-col cols="12" md="3" sm="12" xs="12" class="d-flex justify-end">
          <a justify-content="end">
            <v-icon aria-hidden="false">mdi-share-variant</v-icon>
            Share quote results
          </a>
        </v-col>
      </v-row>
    </v-container>
    
    <v-container>
      <v-row no-gutters>
        <v-col no-gutters cols="12">
          <v-card outlined class="d-flex py-4 px-2 justify-space-between flex-wrap">
           <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Buildings <br> Cover</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  £500,000
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>

            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Buildings <br> Excess</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  £250
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>

            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Contents <br> Cover</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  £50,000
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>
            
            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Contents <br> Excess</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  £250
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>

            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Home <br> Emergency</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  No
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>
            
            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Legal <br> Expenses</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  No
                </v-card-subtitle>
            </div>

            <v-divider vertical></v-divider>

            <div class="text-center">
                <v-card-title
                  class="grey--text"
                >Premium <br> Flex</v-card-title>
                <v-card-subtitle class="black--text text-h6">
                  0%
                </v-card-subtitle>
            </div>

            <v-card-actions>
              <v-btn large tile depressed color="red white--text" class="no-uppercase px-6">
                Change
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-col no-gutters cols="12" sm="12" v-for="insuranceItem in insurance" v-bind:insurance="insurance" v-bind:key="insuranceItem.id">
    
            <v-card v-if="insuranceItem.price != null" outlined class="py-4 px-2 mb-6">
              <v-container >
                <v-row align="center" justify="center">
                  <v-col cols="6" sm="4" md="3">
                    <v-img v-bind:src="require(`../assets/${insuranceItem.logo}`)" v-bind:alt="insuranceItem.insuranceName" contain max-width="150"></v-img>
                  </v-col>  
                  <v-col cols="6" sm="4" md="3"> 
                    <v-card-title class="text-h4 text-sm-h4 text-md-h4 text-lg-h3 my-4">
                      £ {{insuranceItem.price}}
                     
                    </v-card-title>
                    <div v-if="insuranceItem.id == 1" class="ml-4 my-0 pa-0">
                      <p class="text-h6 text-sm-h6 text-md-h6 text-lg-h5 warning--text" >Lowest Price</p>
                    </div>
                   
                    <v-select
                      :items="paymentoptions"
                      label="Payment Plans"
                      outlined
                      flat
                    ></v-select>
                  </v-col>
                  <v-col cols="12" sm="4" md="3">
                    <div class="d-flex flex-column">
                      <div>
                        <p>Buildings accidental damage</p>
                        <div class="d-flex justify-space-between align-center">
                          <div>
                            <p class="text-h5">{{insuranceItem.buildingsAccidentalDamage}}</p>
                          
                          </div>
                          <v-switch
                            v-model="isBuildingsADincluded[insuranceItem.id]"
                            selected
                            inset
                            color="#009BA4"
                            v-on:click="updateBuildingsAD(insuranceItem.id)"
                          ></v-switch>
                        </div>
                      </div>
                      <div>
                        <p>Contents accidental damage</p>
                        <div class="d-flex justify-space-between align-center">
                          
                            <p class="text-h5">{{insuranceItem.contentsAccidentalDamage}}</p>               
                          
                          <v-switch
                            v-model="isContentsADIncluded[insuranceItem.id]"
                            inset
                            color="#009BA4"
                            v-on:click="updateContentsAD(insuranceItem.id)" 
                          ></v-switch>
                        </div>
                      </div>
                    </div>
                  </v-col>
                  <v-col cols="12" sm="4" md="3">
                    <v-card-actions>
                      <v-btn block large tile depressed color="white--text" class="no-uppercase">
                        Apply
                      </v-btn>
                    </v-card-actions>
                  </v-col>
                </v-row>
              </v-container>
              
            </v-card>
            <v-card v-else outlined class="py-4 px-2 mb-6" color="#f2f2f5">
              <v-container>
                <v-row>
                  <v-col cols="6" sm="4" md="3">
                    <v-img v-bind:src="require(`../assets/${insuranceItem.logo}`)" v-bind:alt="insuranceItem.insuranceName" contain max-width="150"></v-img>
                  </v-col>  
                  <v-col cols="6" sm="4" md="9"> 
                    <v-card-title class="text-subtitle-2 text-sm-subtitle-2 text-md-subtitle-2 text-lg-subtitle-2 my-4">
                      Declined to quote
                      <br>! Property too close to a flood plain
                    </v-card-title>
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
      
        </v-col>
      </v-row>
    </v-container>
  </v-sheet>
</template>

<script>
import {insuranceData} from "../seed.js"

export default {
  name: "Results",
  data: function() {
    return {
      insurance: insuranceData,
      paymentoptions: ["Monthly", "Annually", "3 Months Deferred"],
      isBuildingsADincluded: [],
      isContentsADIncluded: [],
    }
  },
  methods: {
    updateBuildingsAD(insuranceId) {
      console.log("checked")
      console.log(insuranceId)
      console.log(this.isBuildingsADincluded)
      this.insurance.map((each) => {
        if(each.id === insuranceId && this.isBuildingsADincluded[insuranceId] == false) {
          console.log(each.buildingsAccidentalDamage )
          console.log(this.isBuildingsADincluded[insuranceId] )
          return each.buildingsAccidentalDamage = "+ £26.92"
        } else if (each.id === insuranceId && this.isBuildingsADincluded[insuranceId] == true) {
          console.log(each.buildingsAccidentalDamage)
          return each.buildingsAccidentalDamage = "Included"
        }
      })
    },
    updateContentsAD(insuranceId) {
      console.log(this.isContentsADIncluded)
      this.insurance.map((each) => {
        if (each.id === insuranceId && this.isContentsADIncluded[insuranceId] == false) {
          return each.contentsAccidentalDamage = "+ £12.67"
        } else if (each.id === insuranceId && this.isContentsADIncluded[insuranceId] == true) {
          return each.contentsAccidentalDamage = "Included"
        }
      })
    },
  }
}
</script>

<style>

  .no-uppercase {
    text-transform: unset !important;
  }

  .v-card__title {
    line-height: 1.2rem !important;
  }


</style>