<template>
    <div class="rs-recent-uploads">
        <RsCard title="Recent Uploads" icon="mdi-folder-multiple-image">
            <v-row class="rs-recent-uploads-container">
                <v-col cols="3" v-for="image in images" :key="image.id">
                    <v-img :src="image.url"></v-img>
                </v-col>
            </v-row>
        </RsCard>
    </div>
</template>

<script>
export default {
    data(){
        return{
            images: [
                {
                    id:1,
                    url:"https://i.picsum.photos/id/1001/5616/3744.jpg?hmac=38lkvX7tHXmlNbI0HzZbtkJ6_wpWyqvkX4Ty6vYElZE",
                },
                {
                    id:2,
                    url:"https://i.picsum.photos/id/1002/4312/2868.jpg?hmac=5LlLE-NY9oMnmIQp7ms6IfdvSUQOzP_O3DPMWmyNxwo",
                },
                {
                    id:3,
                    url:"https://i.picsum.photos/id/1004/5616/3744.jpg?hmac=Or7EJnz-ky5bsKa9_frdDcDCR9VhCP8kMnbZV6-WOrY",
                },
                {
                    id:4,
                    url:"https://i.picsum.photos/id/1006/3000/2000.jpg?hmac=x83pQQ7LW1UTo8HxBcIWuRIVeN_uCg0cG6keXvNvM8g",
                },
                {
                    id:5,
                    url:"https://i.picsum.photos/id/1008/5616/3744.jpg?hmac=906z84ml4jhqPMsm4ObF9aZhCRC-t2S_Sy0RLvYWZwY",
                },
                {
                    id:6,
                    url:"https://i.picsum.photos/id/1016/3844/2563.jpg?hmac=WEryKFRvTdeae2aUrY-DHscSmZuyYI9jd_-p94stBvc",
                },
                {
                    id:7,
                    url:"https://i.picsum.photos/id/1018/3914/2935.jpg?hmac=3N43cQcvTE8NItexePvXvYBrAoGbRssNMpuvuWlwMKg",
                },
                {
                    id:8,
                    url:"https://i.picsum.photos/id/1019/5472/3648.jpg?hmac=2mFzeV1mPbDvR0WmuOWSiW61mf9DDEVPDL0RVvg1HPs",
                },
                {
                    id:9,
                    url:"https://i.picsum.photos/id/1020/4288/2848.jpg?hmac=Jo3ofatg0fee3HGOliAIIkcg4KGXC8UOTO1dm5qIIPc",
                },
                {
                    id:10,
                    url:"https://i.picsum.photos/id/1024/1920/1280.jpg?hmac=-PIpG7j_fRwN8Qtfnsc3M8-kC3yb0XYOBfVzlPSuVII",
                },
                {
                    id:11,
                    url:"https://i.picsum.photos/id/1025/4951/3301.jpg?hmac=_aGh5AtoOChip_iaMo8ZvvytfEojcgqbCH7dzaz-H8Y",
                },
                {
                    id:12,
                    url:"https://i.picsum.photos/id/104/3840/2160.jpg?hmac=Rv0qxBiYb65Htow4mdeDlyT5kLM23Z2cDlN53YYldZU",
                },

            ]
        }
    }
}
</script>