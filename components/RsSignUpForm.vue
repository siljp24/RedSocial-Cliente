<template>
    <div class="rs-sign-up-form mt-4">
        <v-row>
            <v-col class="col-md-6 offset-md-3">
                <v-card>
                    <v-card-title class="justify-center">Sign Up</v-card-title>
                    <v-card-text>
                        <v-file-input placeholder="Avatar" outlined prepend-icon=""></v-file-input>
                        <v-text-field placeholder="Email" type="email" outlined></v-text-field>
                        <v-text-field placeholder="Password" type="password" outlined></v-text-field>
                        <v-text-field placeholder="Repeat Password" type="password" outlined></v-text-field>
                        <v-btn color="success" block>Submit</v-btn>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
        
        
    </div>
</template>