<template>
    <v-row
        class =  'pl-3 pr-3 justify-space-between '

    >
        
        <v-menu
        v-for="room in frequentlyRequestedFrom"
        :key = room.roomId
        open-on-hover
        min-width="200px"
        nudge-right="82px"        
        > 
            <template v-slot:activator="{ on, attrs }">  
            <v-card
                v-bind="attrs"
                v-on='on'
                class='mb-3 pl-4 d-flex align-center'
                min-width=308px

            >
                <v-avatar
                    tile
                    color='#71DDC9'
                    v-text='room.percentage+"%"'  
                    class='white--text font18 font-weight-bold'

                >
                </v-avatar>
                <div>
                <v-card-title 
                class='d-flex font18 weight600'
                v-text='room.requestCount+"Requests"' 
                >
                </v-card-title>
                
                <v-card-subtitle class='roomname' v-text="room.roomName"></v-card-subtitle>
                </div>
            </v-card>
            </template>

            <v-card >
                <v-sheet 
                    class='pt-4 pb-3 d-flex  justify-center ' 
                    color=#E2E9F9
                >
                        <div class='heading weight600'>{{room.roomName}}</div>
                </v-sheet>
                <v-container class='weight600'>
                    
                    <v-row
                        v-for="unit in room.units"
                        :key=unit.unitId
                        class='units '
                    >
                        <v-col 
                        class='d-flex flex-row justify-center font-weight-regular'
                        v-text='unit.unitName' 
                        >
                        </v-col>
                        
                        <v-col>
                            {{unit.requestCount}}({{unit.percentage}})
                        </v-col>
                        
                    </v-row>
                    <v-divider class='ma-3 '></v-divider>
                    <v-row 
                    >
                        <v-col  class='d-flex flex-row justify-center'>Total</v-col>
                        <v-col >
                            {{room.requestCount}}
                        </v-col>
                        
                    </v-row>
                    

                </v-container>
            </v-card>
        </v-menu>
    </v-row>
</template>
<script>
export default {
    props:{
        frequentlyRequestedFrom:Array
    }
}
</script>

<style  scoped>
.weight600{
font-weight: 600;
}

.font18{
font-size:18px;
}

.roomname{
color:#707070;
}

.heading{
    color:#4F78DA;
}
.units{
font-size: 14px;
}
</style>