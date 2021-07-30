<template>
    <v-expansion-panels flat >
    <v-expansion-panel  
      v-for="item in items"
      :key="item.id"
      class="ma-2 " 
      
    >
      <v-expansion-panel-header  >
        <template v-slot:actions>
            <v-icon :color= color>
              mdi-menu-down
            </v-icon>
          </template>
        <div>
        <span class='black--text '>{{item.serviceName}}</span>
        <v-chip
          color=#E2E9F9
          label
          :text-color=color
          large

        >
          {{item.requestCount}} times Requested 
        </v-chip>
        </div>
        <div class = 'text-right '>
        <span class='expansion-header'  > View top and least performing staff</span>
        </div>
      </v-expansion-panel-header>
      <v-expansion-panel-content>
        <Most-requested-services-detail/>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
  
</template>


<script>
export default {
  data(){
    return {
          color:   '#4F78DA',
          items:[   

            {
                "serviceId": "reqNO0763L",
                "serviceName": "Clean room and floor",
                "requestCount": "72",
                "requestedAt": null,
                "id": "1"
            },
            {
                "serviceId": "ke4nZRAn51",
                "serviceName": "Service_rintu",
                "requestCount": "43",
                "requestedAt": null,
                "id": "2"
            },
            {
                "serviceName": "Custom Service",
                "requestCount": "9",
                "requestedAt": null,
                "id": "3"
            },
            {
                "serviceId": "Zx4NwQjGQJ",
                "serviceName": "service-esc-1",
                "requestCount": "4",
                "requestedAt": null,
                "id": "4"
            },
            {
                "serviceId": "J50NdAJ674",
                "serviceName": "test--1",
                "requestCount": "1",
                "requestedAt": null,
                "id": "5"
            },
            {
                "serviceId": "rWmGKQPNPB",
                "serviceName": "service_sanjay",
                "requestCount": "1",
                "requestedAt": null,
                "id": "6"
            }
            ]
    }
  }
}
</script>

<style scoped>

.v-expansion-panel{
  font-weight:600;
}

.expansion-header {
  color:#4F78DA;
}

</style>
