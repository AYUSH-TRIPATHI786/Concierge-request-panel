<template>
    <v-row
        class =  'pl-3 pr-3   d-block d-sm-flex  justify-space-between '

    >
        
        <v-menu
        v-for="(room) in frequentlyRequestedFrom"
        :key = room.roomId
        open-on-hover
        min-width="200px"
        nudge-right="82px"        
        > 
            <template v-slot:activator="{ on, attrs }">  
            <v-col class='col-4'>
            <v-card
                v-bind="attrs"
                v-on='on'
                :class= "'mb-3 pl-4 d-flex align-center col-4' "
                id='request-card'
                min-width=308px
            >
                <v-avatar
                    tile
                    color='#71DDC9'
                    v-text='room.percentage+"%"'  
                    class='white--text per-avatar font-weight-bold'

                >
                </v-avatar>
                <div>
                <v-card-title 
                class='d-flex card-head weight600'
                v-text='room.requestCount+"Requests"' 
                >
                </v-card-title>
                
                <v-card-subtitle class='roomname '  v-text="room.roomName"></v-card-subtitle>
                </div>
            </v-card>
            </v-col>
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
                        class='units font-weight-regular'
                    >
                        <v-col 
                        class='ml-4  '
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
                        <v-col  class='ml-4'>Total</v-col>
                        <v-col >
                            {{room.requestCount}}
                        </v-col>
                        
                    </v-row>
                    

                </v-container>
            </v-card>
            
        </v-menu>
        <v-col>
            
        </v-col>
    </v-row>
</template>
<script>
export default {
    props:{
        frequentlyRequestedFrom:Array
    },
    methods:{
        request_card_classes(){
            let classes =  "";
            (index===frequentlyRequestedFrom.length-2 && 'mr-auto')
        }
    }

}
</script>

<style  scoped>

.weight600{
font-weight: 600;
}

.card-head{
font-size:18px;
}

.per-avatar{
font-size:18px;
}

.roomname{
color:#707070;
font-size:16px;
}

.heading{
    color:#4F78DA;
}
.units{
font-size: 14px;
}

#request-card{
box-shadow: 0px 16px 25px 2px rgba(39, 83, 187, 0.02);
}
</style>

<style lang="scss" scoped>
    @import '~vuetify/src/styles/styles.sass';
    @media #{map-get($display-breakpoints, 'xs-only')}{
        .card-head{
        font-size:12px;
        line-height: 16px;
        }
        .roomname{
        font-size:10px;
        line-height: 14px;
        }
        .per-avatar{
        font-size:14px;
        }
    }
</style>
