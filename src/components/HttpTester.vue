<script lang="ts">
import axios from 'axios'

export default {
    data() {
        return {
            json_placeholder: {},
            first_name: "Test",
            last_name: "Name",
            names: [
                {
                    first_name: "First",
                    last_name: "Name"
                },
                {
                    first_name: "Second",
                    last_name: "Name"
                },
                {
                    first_name: "Third",
                    last_name: "Name"
                },
            ]
        }
    },
    methods: {
        writeName: function (first_name: any, last_name: any) {
            axios.put('https://django/name/writeOne')
        },

        getNames: function () {
            axios.get('http://localhost:8000/names/')
                .then((response) => {
                    console.log(response.data)
                    this.names = response.data
                })
        }
    }
}
</script>

<template>
    <div>
        <v-container>
            <v-text-field label="First name"></v-text-field>
            <v-text-field label="Last name"></v-text-field>
            <v-btn>
                Send name to database
            </v-btn>
        </v-container>
        <v-container>
            <v-list>
                <v-list-item v-for="item in names" :key="item.last_name">
                    <v-list-item-title>{{ item.first_name }} {{ item.last_name }}</v-list-item-title>
                </v-list-item>
            </v-list>
            <v-btn @click="getNames()">
                Acutalize names from database
            </v-btn>
        </v-container>
    </div>
</template>

