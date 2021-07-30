<template>
    <v-container class='white font-weight-regular'>
        <v-row class='table-header'>
            <v-col>
                Name
            </v-col>
            <v-col>
                Requests Closed
            </v-col>
            <v-col>
                Average TAT
            </v-col>
        </v-row>
        <v-row 
            v-for="staff in staffsList"
            :key = staff.id
        >
            <v-col v-text='staff.name'>            </v-col>
            <v-col v-text='staff.requestCount'>            </v-col>
            <v-col v-text="staff.avgTat">            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    props:{
        staffsList:Array
    },
}
</script>
<style scoped>
.table-header{
    color:#6D6D6D;
}
</style>
