<template>
    <div class="rs-card">
         <v-card>
            <v-card-title class="rs-card-title"
                v-if="header"
                :class="remove ? 'rs-card-title rs-remove' : 'rs-card-title rs-black'"
                >

                <div v-if="remove" class="d-flex justify-space-between rs-card-remove">
                    <p class="headline mx-2 white--text">{{ title }}</p>
                    <v-btn color="error">Delete</v-btn>
                </div>
                <div v-else class="d-flex justify-start rs-card-no-remove">
                    <v-icon size="32" class="mt-n3" color="white">{{ icon }}</v-icon>
                    <p class="headline mx-2 white--text">{{ title }}</p>
                </div>
            </v-card-title>
            <v-card-text class="rs-card-text pa-1">
               <div class="rs-card-text-container pa-2">
                   <slot />
               </div>
            </v-card-text>
        </v-card>
    </div>
</template>

<script>
export default {
    props:{
        title:{
           type: String,
        },
        icon:{
            type:String,
            required: false,
            default: undefined,
        },
        remove:{
            type: Boolean,
            default: false,
        },
        header:{
            type: Boolean,
            default: true,
        }
    }
}
</script>

<style scoped>
    .rs-card-title{
        height: 60px;
    }
    .rs-remove{
        background-color: rgb(153, 104, 153);
    }
    .rs-black{
        background-color: rgb(39, 39, 39);
    }
    .rs-card-text-container{
        background-color: white;
    }
    .rs-card-text{
        background-color: rgb(39, 39, 39);
    }
    .rs-card-remove{
        width: 100%;
    }
</style>
