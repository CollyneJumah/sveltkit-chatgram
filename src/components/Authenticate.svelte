<script lang="ts">

let email=""
let password=""
let confirpassword=""
let error=false
let register = false

function handleAuthentication(){
    if(!email || !password || (register && ! confirpassword)){
        error= true
        return
    }
}
</script>

<div class="authContainer">
	<form action="" autocomplete="off">
		<h1>{ register? 'Register' : 'Login'}</h1>
        {#if error}
            <p class="error">Information entered is incorrect. Please try again!</p>
        {/if}
		<label for="email">
            <p class={email ? "above" : "center"}>Email</p>
			<input bind:value={email} type="email" name="email" id="" placeholder="Enter your email address"/>
		</label>
		<label for="password">
            <p class={password ? "above" : "center"}>password</p>
			<input bind:value={password} type="password" name="email" id="" placeholder="Enter your password"/>
		</label>
		<label for="password">
            <p class={confirpassword ? "above" : "center"}>password again</p>
			<input bind:value={confirpassword} name="confirm-password" type="password" id="" placeholder="Password again"/>
		</label>
        <button type="button">Submit</button>
	</form>
</div>

<style>
	.authContainer {
		display: flex;
		flex-direction: column;
		align-items: center;
        justify-content: center;
        flex: 1;
        transition-duration: 200ms;
	}
    h1{
        text-align: center;
        font-size: 3rem;
    }
    form{
        display: flex;
        flex-direction: column;
        gap: 14px;
        width: 400px;
        max-width: 100%;
        margin: 0 auto;
        padding: 24px;
    }
    form label{
        position: relative;
        border: 1px solid rgb(62, 62, 210);
        border-radius: 5px;
    }
    form label:focus-within{
        border-color: blue;
    }
    form input{
        width: 100%;
        padding: 14px;
        border: none;
        background: transparent;
        color: white;
    }
    form input:focus{
        border: none;
        outline: none;
    }
    form button{
        background-color: blue;
        color: white;
        border: none;
        padding: 10px 0;
        border-radius: 5px;
        cursor: pointer;
    }
    form button:hover{
        background-color: transparent;
        animation-duration: 300ms;
        animation-delay: 500ms;
        border: 1px solid blue;

    }
   .above, .center{
    position: absolute;
    transform: translateY(-50%);
    pointer-events: none;
    color: white;
    border-radius: 5px;
    padding: 0 6px;
    font-size: 0.8rem;
   }
   .above{
    top: 0;
    left:15px;
    background-color: blue;
    border: 1px solid blue;
    font-size: 0.8rem;
   }
   .center{
    top: 50%;
    left: 6px;
    border: 1px solid transparent;
    opacity: 0;
   }
   .error{
    color: coral;
    font-size: 0.9rem;
   }
   </style>
