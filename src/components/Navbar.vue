<template>
    <nav class="navbar align-self-start">
        <div class="container">
            <div class="col-2"></div>
            <div class="col-2">
                <img @click="changeTheme" style="cursor: pointer;" :src="checkTheme()" width="100" height="100" class="img-fluid" alt="a">
            </div>

        </div>
    </nav>
</template>
<script>
export default{
    data(){
        return{
            theme: 'Light'
        }
    },
    methods:{
        changeTheme(e){
            this.theme == 'Light' ? this.theme = 'Dark' : this.theme = "Light";
        },
        checkTheme(){
            if(this.theme == 'Light'){
                return 'https://repository-images.githubusercontent.com/463612134/d106e3cd-9f44-4b5f-af09-8a703b0427a5'
            }else if(this.theme == 'Dark'){
                return 'https://panzerstadt.gallerycdn.vsassets.io/extensions/panzerstadt/light-dark-toggle/0.2.0/1581516336260/Microsoft.VisualStudio.Services.Icons.Default'
            }
        }
    }
    
}
</script>
