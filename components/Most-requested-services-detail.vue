<template>
    <div>
        <v-row class='mt-3'>
            <v-col class='col-12 col-sm-6'>
                <v-container>
                    <v-row >Top Performing Skills</v-row>
                </v-container>
                <Performing-staff-list :staffsList='topPerformingStaffs' />
            </v-col>
            <v-col class='col-12 col-sm-6' >
                <v-container>
                    <v-row >Least Performing Skills</v-row>
                </v-container>
                <Performing-staff-list :staffsList='leastPerformingStaffs' />
            </v-col>  
        </v-row>
        <v-row>
            <v-col>Frequently Requested From</v-col>
        </v-row>
        <Frequently-requested-from-list :frequentlyRequestedFrom="frequentlyRequestedFrom"/>
    </div>
</template>

<script>
import FrequentlyRequestedFromList from './Frequently-Requested-From-list.vue'
import PerformingStaffList from './Performing-staff-list.vue'
export default {
  components: { PerformingStaffList, FrequentlyRequestedFromList },
    data(){
        return {
        "topPerformingStaffs": [
            {
                "id": "Zx4NwKjNQJ",
                "name": "hk_user_2",
                "avgTat": 13008,
                "requestCount": "2",
                "requestedAt": null
            },
            {
                "id": "Rk06kQnBQx",
                "name": "HK User 2",
                "avgTat": 22195,
                "requestCount": "3",
                "requestedAt": null
            }
        ],
        "leastPerformingStaffs": [
            {
                "id": "Rk06kQnBQx",
                "name": "HK User 2",
                "avgTat": 22195,
                "requestCount": "3",
                "requestedAt": null
            },
            {
                "id": "Zx4NwKjNQJ",
                "name": "hk_user_2",
                "avgTat": 13008,
                "requestCount": "2",
                "requestedAt": null
            }
        ],
        "frequentlyRequestedFrom": [
            {
                "roomId": "gxyGxdbGkB",
                "roomName": "asd2",
                "requestCount": "15",
                "percentage": 25,
                "units": [
                    {
                        "roomId": "gxyGxdbGkB",
                        "unitId": "8q6JqxAN2Y",
                        "unitName": "asd1",
                        "requestCount": "15",
                        "percentage": 100,
                        "requestedAt": null,
                        "id": ""
                    }
                ],
                "requestedAt": null,
                "id": ""
            },
            {
                "roomId": "7oK6zA7Nb3",
                "roomName": "asd22",
                "requestCount": "15",
                "percentage": 25,
                "units": [
                    {
                        "roomId": "7oK6zA7Nb3",
                        "unitId": "wZG1EzPGY5",
                        "unitName": " ",
                        "requestCount": "15",
                        "percentage": 100,
                        "requestedAt": null,
                        "id": ""
                    }
                ],
                "requestedAt": null,
                "id": ""
            },
            {
                "roomId": "8ePNB15n1J",
                "roomName": "General ward",
                "requestCount": "11",
                "percentage": 18,
                "units": [
                    {
                        "roomId": "8ePNB15n1J",
                        "unitId": "ZjGeRAgn94",
                        "unitName": "B2",
                        "requestCount": "8",
                        "percentage": 73,
                        "requestedAt": null,
                        "id": ""
                    },
                    {
                        "roomId": "8ePNB15n1J",
                        "unitId": "WrNljAjG7J",
                        "unitName": "B1",
                        "requestCount": "3",
                        "percentage": 27,
                        "requestedAt": null,
                        "id": ""
                    }
                ],
                "requestedAt": null,
                "id": ""
            },
            {
                "roomId": "5WrNlAx67J",
                "roomName": "Room 1",
                "requestCount": "10",
                "percentage": 17,
                "units": [
                    {
                        "roomId": "5WrNlAx67J",
                        "unitId": "DqNW4jw6wJ",
                        "unitName": "bed 1",
                        "requestCount": "8",
                        "percentage": 80,
                        "requestedAt": null,
                        "id": ""
                    },
                    {
                        "roomId": "5WrNlAx67J",
                        "unitId": "BDn9XJZGYK",
                        "unitName": "Bed 1",
                        "requestCount": "2",
                        "percentage": 20,
                        "requestedAt": null,
                        "id": ""
                    }
                ],
                "requestedAt": null,
                "id": ""
            },
            {
                "roomId": "reqNOvjn3L",
                "roomName": "Room B",
                "requestCount": "9",
                "percentage": 15,
                "units": [
                    {
                        "roomId": "reqNOvjn3L",
                        "unitId": "kY6jvA4619",
                        "unitName": "BED 1",
                        "requestCount": "9",
                        "percentage": 100,
                        "requestedAt": null,
                        "id": ""
                    }
                ],
                "requestedAt": null,
                "id": ""
            }
        ]

        }
    }
}
</script>
