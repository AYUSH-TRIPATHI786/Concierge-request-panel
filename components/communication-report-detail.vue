<template>
    <div>
        <v-row
        v-for="item in items"
        :key='item.id'
        class='mr-3 mt-1 font-weight-regular text-center'
        >
          <v-col sm='3' class='text-left'><span >{{item.name}}</span></v-col>
          <v-col ><span >{{item.toRequesters}}</span></v-col>
          <v-col ><span >{{item.toDepartmentStaff}}</span></v-col>
          <v-col ><span >{{item.toDepartmentAdmin}}</span></v-col>
          <v-col ><span >{{item.toHospitalAdmin}}</span></v-col>
          <v-col ><span >{{item.toOrganizationAdmin}}</span></v-col>
        </v-row>
        
    </div>
</template>

<script>
export default {
    data(){
        return {
        items:[
        {   
            'name':'Request Creation',
            'toRequesters':200,
            'toDepartmentStaff':50,
            'toDepartmentAdmin':30,
            'toHospitalAdmin':15,
            'toOrganizationAdmin':5,
            "requestedAt": null,
            "id": "1"                
        },
        {   
            'name':'Request Completion',
            'toRequesters':200,
            'toDepartmentStaff':50,
            'toDepartmentAdmin':30,
            'toHospitalAdmin':15,
            'toOrganizationAdmin':5,
            "requestedAt": null,
            "id": "2"                
        },{   
            'name':'Request Cancelled',
            'toRequesters':200,
            'toDepartmentStaff':50,
            'toDepartmentAdmin':30,
            'toHospitalAdmin':15,
            'toOrganizationAdmin':5,
            "requestedAt": null,
            "id": "3"                
        },{   
            'name':'Request Escalation',
            'toRequesters':200,
            'toDepartmentStaff':50,
            'toDepartmentAdmin':30,
            'toHospitalAdmin':15,
            'toOrganizationAdmin':5,
            "requestedAt": null,
            "id": "1"                
        }   
        ]

        }
    }
}
</script>

<style lang="scss" scoped>

@import '~vuetify/src/styles/styles.sass';
@media #{map-get($display-breakpoints, 'xs-only')}{
    .span{
        font-size:10px
    }    
}

</style>