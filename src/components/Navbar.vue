<template>
    <nav class="navbar align-self-start">
        <div class="container">
            <div class="col-2">
                <div class="dropdown">
                    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                        Language | زبان
                    </button>
                    <ul class="dropdown-menu bg-info text-light" aria-labelledby="dropdownMenuButton1">
                        <li class="ms-1">English</li>
                        <li class="text-end me-1">فارسی</li>
                    </ul>
                </div>
            </div>
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
                return 'https://i.ibb.co/bmbHzxg/t.png'
            }
        }
    }
    
}
</script>
