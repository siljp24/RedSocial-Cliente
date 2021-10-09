<template>
    <div class="rs-stats">
        <!-- <v-card dark>
            <v-card-title class="rs-card-title">
                <v-icon size="32" class="mt-n3">mdi-chart-box</v-icon>
                <p class="headline mx-2">Stats</p>
            </v-card-title>
            <v-card-text class="rs-card-text pa-1"> -->
        <RsCard title="Stats" icon="mdi-chart-box">
                <v-list>
                    <v-list-item>
                        <v-list-item-icon><v-icon>mdi-file-image</v-icon></v-list-item-icon>
                        <v-list-item-content>n# images</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-comment</v-icon></v-list-item-icon>
                        <v-list-item-content>n# comments</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-eye-settings</v-icon></v-list-item-icon>
                        <v-list-item-content>n#views</v-list-item-content>
                    </v-list-item>
                     <v-list-item>
                        <v-list-item-icon><v-icon>mdi-thumb-up</v-icon></v-list-item-icon>
                        <v-list-item-content>n#likes</v-list-item-content>
                    </v-list-item>
                </v-list>
        </RsCard>
            <!-- </v-card-text>
        </v-card> -->
    </div>
</template>


