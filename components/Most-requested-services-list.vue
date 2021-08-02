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
        <div class=' d-flex flex-column flex-sm-row align-baseline'>
          <span class='mb-1 mr-1 ' >{{item.serviceName}}</span>
          <v-chip
            color=#E2E9F9
            :text-color=color
            :x-small='$vuetify.breakpoint.xs'
            label
            class=''
          >
            <div class='chip'>{{item.requestCount}} times Requested</div> 
          </v-chip>
        </div>
        <div class = 'text-right '>
        <span class='expansion-header d-none d-sm-flex flex-row-reverse'  > View top and least performing staff</span>
        </div>
      </v-expansion-panel-header>
      <v-expansion-panel-content color="#F8F9FD">
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
          large: true,
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

.chip{
  font-size: 8px;
}
</style>

<style lang="scss" scoped>
  @import '~vuetify/src/styles/styles.sass';
  @media #{map-get($display-breakpoints, 'xs-only')}{
    .v-expansion-panel{
      font-size:10px;
    }
    .v-expansion-panel-header{
      font-size:10px;
    }
    
  }

</style>
