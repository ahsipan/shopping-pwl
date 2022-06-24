<template>
    <form @submit.prevent="handleSubmit">
        <h3>Login</h3>

        <div class="form-group">
            <label>Email</label>
            <input type="email" class="form-control" v-model="email" placeholder="Email"/>

        </div>
        <div class="form-group">
            <label>Password</label>
            <input type="password" class="form-control" v-model="password" placeholder="Password"/>

        </div>
        <button class="btn btn-primary btn-block">Login</button>
    </form>
</template>

<script>
export default{
    name: "Login",
    data(){
        return{
            email:'',
            password: ''
        }
    },
    methods:{
        handleSubmit(){
            if (localStorage.getItem('email')==this.email){
                if(localStorage.getItem('password')==this.password){
                    alert('Login Berhasil')
                    this.$router.push('/productlist')
                }
            }else{
                alert('Login Gagal')
            }
        }
        // async handleSubmit(){
        //     const response = await axios.post('login', {
        //         email: this.email,
        //         password: this.password
        //     });
        //     localStorage.setItem('token', response.data.token)
        //     this.$router.push('/productlist');

        // }
    }
}
</script>