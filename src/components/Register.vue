<template>
    <form @submit.prevent="handleSubmit">
        <h3>Sign Up</h3>
        <div class="form-group">
            <label>Username</label>
            <input type="text" class="form-control" v-model="username" placeholder="Username"/>
        </div>
        <div class="form-group">
            <label>Email</label>
            <input type="email" class="form-control" v-model="email" placeholder="Email"/>
        </div>
        <div class="form-group">
            <label>Password</label>
            <input type="password" class="form-control" v-model="password" placeholder="Password"/>
        </div>
        <button class="btn btn-primary btn-block">Sign Up</button>
    </form>
</template>

<script>
    export default{
        name: 'Register',
        data(){
            return {
                username: '',
                email: '',
                password: '',
            }
        },
        methods: {
            handleSubmit(){
                localStorage.setItem('username',this.username)
                localStorage.setItem('email',this.email)
                localStorage.setItem('password',this.password)
                alert('REGISTER SUKSES, SILAKAN LOGIN!')
                this.username = ''
                this.email = ''
                this.password = ''
            }
            // async handleSubmit(){
            //     await axios.post('register', {
            //         username : this.username,
            //         email : this.email,
            //         password : this.password
            //     });
            //     this.$router.push('/login');
            // }
        }
    }
</script>