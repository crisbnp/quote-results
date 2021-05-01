<template>
  <v-sheet max-width="max-content" class="pt-0">
    <v-container>
      <v-row>
        <v-col cols="2">
          <v-img 
            src="../assets/defaqto-expert-rated.png"
            width="150"
            alt="defaqto 5 star home insurance"
          ></v-img>
        </v-col>
        <v-col cols="7">
          <h1>Your home insurance quotes <br> for Jen Pomfret</h1>
        </v-col>
        <v-col cols="3" class="d-flex justify-end">
          <a justify-content="end">
            <v-icon aria-hidden="false">mdi-share-variant</v-icon>
            Share quote results
          </a>
        </v-col>
      </v-row>
    </v-container>
    
    <v-container>
      <v-row>
        <v-col no-gutters col="12">
          <v-card outlined class="d-flex py-4 px-2 justify-space-between">
           <div class="text-center">
                <v-card-title
                  class="grey--text wordbreak"
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
                  class="grey--text wordbreak"
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
        <v-col no-gutters col="12">
          <v-card outlined class="d-flex py-4 px-2 justify-space-between">
            
            <img v-bind:src="`../assets/${insurance[0].logo}`" v-bind:alt="insurance[0].insuranceName"/>
            <v-card-title>
              £ {{insurance[0].price}}
            </v-card-title>
            <v-overflow-btn
              :items="paymentoptions"
              label="Monthly"
              segmented
              outlined
              flat
            ></v-overflow-btn>
            <div>
              <p>Builldings accidental damage</p>
              <div v-if="isBuildingsADincluded === false">
                <p>+ {{insurance[0].buildingsAccidentalDamage}}</p>
              
              </div>
              <div v-else>
                <p>Included</p>
              </div>
              <v-switch
                v-model="isBuildingsADincluded"
                inset
                color="#009BA4"
              ></v-switch>
              
            </div>
            <div>
              <p>Contents accidental damage</p>
              <div v-if="isContentsADIncluded === false">
                <p>+ {{insurance[0].buildingsAccidentalDamage}}</p>
              
              </div>
              <div v-else>
                <p>Included</p>
              </div>
              <v-switch
                v-model="isContentsADIncluded"
                inset
                color="#009BA4"
              ></v-switch>
              
            </div>
            <v-card-actions>
              <v-btn large tile depressed color="white--text" class="no-uppercase px-10">
                Apply
              </v-btn>
            </v-card-actions>
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
      isBuildingsADincluded: false,
      isContentsADIncluded: false
    }
  },
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