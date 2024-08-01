<script>
  /** @type {import('./$types').Actions} */
  export let form;
</script>

<div class="mt-10 pt-10 w-full max-w-xl p-12 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg">
  <form method="POST" action="?/login">
    <div class="flex flex-wrap -mx-3 mb-2">
      <div class="w-full px-3 mb-6 md:mb-0">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="email">
          Email
        </label>
        <input
          class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          id="email"
          type="text"
          placeholder="Enter email"
          name="email"
          style="height: 40px; width: 100%;"
        />
      </div>
      <div class="w-full px-3 mb-6 md:mb-0 mt-4">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="password">
          Password
        </label>
        <input
          class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          id="password"
          type="text"
          placeholder="Enter password"
          name="password"
          style="height: 40px; width: 100%;"
        />
      </div>
    </div>
    <button
      type="submit"
      class="bg-yellow-500 hover:bg-blue-700 text-white font-bold mt-5 px-4 py-2 rounded"
      style="height: 40px; width: 100px;"
    >
      Login
    </button>
  </form>
  {#if form?.success}
    <!-- this message is ephemeral; it exists because the page was rendered in
           response to a form submission. it will vanish if the user reloads -->
    <p class="pt-2">Logged in!!</p>
    <p>Your balance is {form?.balance.data.balance.summary}</p>
  {/if}
</div>

<div class="m-20 pt-10 w-full max-w-xl p-12 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg">
  <form method="POST" action="?/pay">
    <div class="flex flex-wrap -mx-3 mb-2">
      <div class="w-full px-3 mb-6 md:mb-0">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="email">
          Email
        </label>
        <input
          class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          id="email"
          type="text"
          placeholder="Enter email"
          name="email"
          style="height: 40px; width: 100%;"
        />
      </div>
      <div class="w-full px-3 mb-6 md:mb-0 mt-4">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="password">
          Password
        </label>
        <input
          class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          id="password"
          type="text"
          placeholder="Enter password"
          name="password"
          style="height: 40px; width: 100%;"
        />
      </div>
    </div>
    <div class="w-full px-3 mb-6 md:mb-0">
      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="paymail">
        Paymail
      </label>
      <input
        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
        id="paymail"
        type="text"
        placeholder="Enter paymail"
        name="paymail"
        style="height: 40px; width: 100%;"
      />
    </div>
    <div class="w-full px-3 mb-6 md:mb-0 mt-4">
      <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="amount">
        Amount
      </label>
      <input
        class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
        id="amount"
        type="number"
        placeholder="Enter amount"
        name="amount"
        style="height: 40px; width: 100%;"
      />
    </div>
    <button
      type="submit"
      class="bg-yellow-500 hover:bg-blue-700 text-white font-bold mt-5 px-4 py-2 rounded"
      style="height: 40px; width: 100px;"
    >
      Pay
    </button>
  </form>
  {#if form?.success}
    <!-- this message is ephemeral; it exists because the page was rendered in
           response to a form submission. it will vanish if the user reloads -->
    <p class="pt-2">Payment successful!!</p>
    <p>Your transaction is <a href="{form?.payment}">transcation</a></p>
  {/if}
</div>
