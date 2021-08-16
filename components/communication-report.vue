<template>
  <v-sheet 
  color="#E5E5E5"
  >
    <v-container
    class = 'com-report '
    >
      <v-card
        flat
        class= 'mb-2 pt-3 pb-2 pl-6 pr-6 overflow-hidden'
      >
        <v-row
          class='mr-3 font-weight-regular header  '    
        >
            <v-col
            class='col-3 d-flex align-center '
            >
              <span >
                General
              </span>
              <v-menu offset-y>
                <template v-slot:activator="{ on, attrs }">
                    <v-icon 
                      small
                      v-bind="attrs"
                      v-on='on'
                      :x-small='$vuetify.breakpoint.xs'
                    >
                      $expand
                    </v-icon>
                </template>
                <v-list>
                  <v-list-item
                    v-for="(dep, index) in departments"
                    :key="index"
                  >
                    <v-list-item-title>{{ dep.name}}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>
            </v-col>  

            <v-col 
            v-for="cat in categories"
            :key=cat
            class='text-center '
            >
              <div>To</div>
              <div  >
                {{cat}} 
              </div>
            </v-col>
        
        </v-row>  
      </v-card>
      <v-expansion-panels 
      flat 
      multiple
      >
      <v-expansion-panel  
        v-for="item in items"
        :key="item.id"
        class=" mt-2 mb-2 " 
        
      >
        <v-expansion-panel-header  >
          <template v-slot:actions>
            <v-icon 
            :color= iconcolor
            >
              mdi-menu-down
            </v-icon>
          </template>
          <v-row
          class='text-center'
          >
            <v-col class='col-3 text-left' ><span  >{{item.name}}</span></v-col>
            <v-col ><span >{{item.toRequesters}}</span></v-col>
            <v-col ><span >{{item.toDepartmentStaff}}</span></v-col>
            <v-col ><span >{{item.toDepartmentAdmin}}</span></v-col>
            <v-col ><span >{{item.toHospitalAdmin}}</span></v-col>
            <v-col ><span >{{item.toOrganizationAdmin}}</span></v-col>
          </v-row>
        </v-expansion-panel-header>
        <v-expansion-panel-content color="#F8F9FD">
          <communication-report-detail/>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
    </v-container>
  </v-sheet>
</template>


<script>
export default {
  data(){
    return {
          iconcolor:'#4F78DA',

          departments:[
            {
            'name':'Option1',
            },
            {
            'name':'Option2'
            }
          ],
          
          categories:[
              'Patients/Requesters',
              'Department Staff',
              'Department Admin',
              'Hospital Admin',
              'Organization Admin',
              ],
          items:[
            {   
              'name':'OTP',
              'toRequesters':200,
              'toDepartmentStaff':50,
              'toDepartmentAdmin':30,
              'toHospitalAdmin':15,
              'toOrganizationAdmin':5,
              "requestedAt": null,
              "id": "1"                
            },
            {   
              'name':'Maintainance',
              'toRequesters':200,
              'toDepartmentStaff':50,
              'toDepartmentAdmin':30,
              'toHospitalAdmin':15,
              'toOrganizationAdmin':5,
              "requestedAt": null,
              "id": "2"                
            },{   
              'name':'HouseKeeping',
              'toRequesters':200,
              'toDepartmentStaff':50,
              'toDepartmentAdmin':30,
              'toHospitalAdmin':15,
              'toOrganizationAdmin':5,
              "requestedAt": null,
              "id": "3"                
            },{   
              'name':'Electrical Departmnet',
              'toRequesters':200,
              'toDepartmentStaff':50,
              'toDepartmentAdmin':30,
              'toHospitalAdmin':15,
              'toOrganizationAdmin':5,
              "requestedAt": null,
              "id": "1"                
            },{   
              'name':'IT Department',
              'toRequesters':200,
              'toDepartmentStaff':50,
              'toDepartmentAdmin':30,
              'toHospitalAdmin':15,
              'toOrganizationAdmin':5,
              "requestedAt": null,
              "id": "1"                
            },
            
            ]
    }
  }
}
</script>

<style lang="scss" scoped>
.v-sheet{
  overflow-y:auto;
  .com-report{
    min-width:800px;
    .header{
      color: #6D6D6D;
      font-size: 12px;
    }

    .v-expansion-panel{
      font-weight:600;
    }
}
}
@import '~vuetify/src/styles/styles.sass';
@media #{map-get($display-breakpoints, 'xs-only')}{
  .v-sheet{
    .com-report{
      .header{
        font-size: 8px;
      }
      .v-expansion-panel{
        font-size:10px;
        .v-expansion-panel-header{
          font-size:10px;
        }
      }
    }
  }
}


</style>
