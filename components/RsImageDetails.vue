<template>
    <div class="rs-image-details">
        <RsCard :title="title" remove>
            <div class="rs-image-details-container">
                <v-img src="https://i.picsum.photos/id/1079/4496/3000.jpg?hmac=G-dJcpU08vEMqjUz2rb3IxjOG99rcePqW9BF1IsPLf0" height="400px"/>
                <div class="rs-image-details-container-description">
                    <p class="headline font-weight-black">{{title}}</p>
                    <p>{{description}}</p>
                </div>
                <div class="rs-image-details-container-info d-flex">
                    <div class="rs-image-details-container-info-start d-flex justify-start">
                        <v-btn color="success">
                            <v-icon class="mx-2">mdi-thumb-up</v-icon>
                            Like
                        </v-btn>
                        <div class="mx-12">
                            <v-icon class=" d-flex justify-center">mdi-cards-heart</v-icon>
                            <p>Likes</p>
                        </div>
                        <div class="mx-12">
                            <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
                            <p>View</p>
                        </div>
                    </div>
                    <v-spacer></v-spacer>
                    <div class="rs-image-details-container-info-end">
                        <p>08/10/2021</p>
                    </div> 
                </div>
            </div>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            title:"Image title",
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tempus faucibus ipsum, ac volutpat tellus molestie id. Aliquam elementum accumsan nisi, imperdiet finibus dolor sagittis id. Donec congue justo convallis.'
        }
    }
}
</script>