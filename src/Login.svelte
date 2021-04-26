<script>
    import {link} from 'svelte-spa-router'
    import axios from 'axios';
    import {push} from 'svelte-spa-router'
    let username,password;

    async function login(){
      const result=await axios.post("http://localhost:8090/projectwork/rest/utente/login", {
        username, password
      })
      console.log(result)
      console.log(result.data.resultTest)
      if(result.data.resultTest){
        console.log("entrato")
        sessionStorage.setItem("utente", JSON.stringify(result.data.result))
        console.log(result)
        push("/")
      }
    }
</script>

<section class="text-gray-600 body-font">
    <centre>
    <div class="container px-5 py-24 mx-auto flex flex-wrap items-center">
      <div id="login" class="lg:w-2/6 md:w-1/2 bg-gray-100 rounded-lg p-8 flex flex-col md:ml-auto w-full mt-10 md:mt-0">
        <h2 class="text-gray-900 text-lg font-medium title-font mb-5">Sign In</h2>
        <div class="relative mb-4">
          <label for="full-name" class="leading-7 text-sm text-gray-600">Username</label>
          <input bind:value={username} type="text" id="full-name" name="full-name" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <div class="relative mb-4">
          <label for="password" class="leading-7 text-sm text-gray-600">Password</label>
          <input bind:value={password} type="password" id="psw" name="password" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <button on:click={login} class="text-white bg-yellow-500 border-0 py-2 px-8 focus:outline-none hover:bg-yellow-600 rounded text-lg">Invia</button>
        <p>Non sei registrato? <a href="/signup" use:link>Sign Up</a></p>
      </div>
    </div>
  </section>

  <style>
      #login{
          margin: auto;
      }
  </style>