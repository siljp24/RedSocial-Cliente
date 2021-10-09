<template>
    <div class="rs-upload">
        <RsCard title="Upload" icon="mdi-cloud-upload">
            <div class="rs-upload-container">
               <v-form>
                   <v-file-input outlined prepend-icon="" placeholder="File"></v-file-input>
                   <v-text-field outlined name="title" placeholder=" Image Title"></v-text-field>
                   <v-textarea outlined name="description" placeholder="Description"></v-textarea>
                   <div class="rs-btn-container d-flex justify-end">
                        <v-btn color="success" type="submit">Submit</v-btn>
                   </div>

                </v-form> 
            </div>
        </RsCard>
    </div>
</template>