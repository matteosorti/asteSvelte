<script>
    import {link} from 'svelte-spa-router'
</script>


<section class="text-gray-600 body-font">
    <centre>
    <div class="container px-5 py-24 mx-auto flex flex-wrap items-center">
      <div id="login" class="lg:w-2/6 md:w-1/2 bg-gray-100 rounded-lg p-8 flex flex-col md:ml-auto w-full mt-10 md:mt-0">
        <h2 class="text-gray-900 text-lg font-medium title-font mb-5">Sign Up</h2>
        <div class="relative mb-4">
          <label for="full-name" class="leading-7 text-sm text-gray-600">Username</label>
          <input type="text" id="full-name" name="full-name" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <div class="relative mb-4">
          <label for="email" class="leading-7 text-sm text-gray-600">Email</label>
          <input type="email" id="email" name="email" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <div class="relative mb-4">
            <label for="password" class="leading-7 text-sm text-gray-600">Password</label>
            <input type="password" id="psw" name="password" class="w-full bg-white rounded border border-gray-300 focus:border-yellow-500 focus:ring-2 focus:ring-yellow-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
        </div>
        <button class="text-white bg-yellow-500 border-0 py-2 px-8 focus:outline-none hover:bg-yellow-600 rounded text-lg">Invia</button>
        <p>Sei già registrato? <a href="/login" use:link>Sign In</a></p>
      </div>
    </div>
  </section>

  <style>
      #login{
          margin: auto;
      }
  </style>