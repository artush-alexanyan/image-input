<template>
    <div class="image-field">
        <div class="container">
            <div class="h4 text-center text-primary mt-5">
                Image Field Component
            </div>
            <div class="row mt-5">
                <div class="col col-6">
                    <label for="">
                            Change image 
                            <strong>src</strong>
                    </label>
                    <p class="text-center text-secondary">
                        Available src's 
                        <strong>
                            (vue.png, angular.jpeg, react.png)
                        </strong>
                    </p>
                    <input type="text" 
                           class="form-control"
                           v-model="image"
                        >
                </div>
                <div class="col col-4">
                    <div class="card">
                        <input type="image" 
                               :src='require("../assets/" + validimages)'
                            >
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'fieldImage',
    data: () => ({
        defaultImage: 'undefinde.png',
        image: '',
        images: ['vue.png', 'angular.jpeg', 'react.png']
    }),
    computed: {
        validimages () {
            return this.images.includes(this.image) ? this.image : this.defaultImage
            }     
        }
}
</script>

