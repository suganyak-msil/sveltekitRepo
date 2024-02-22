<script>
    let formData = {
      name: "",
      query: "",
      location: "",
      activeUser: false,
      date: "",
    };
  
    let submitted = false;
  
    function submitForm(event) {
      event.preventDefault();
      console.log(formData);
      submitted = true;
    }
  </script>
  
  <!-- <div>
    <pre>
      {JSON.stringify(formData,null,2)}
    </pre>
  </div> -->
  
  <div class="flex flex-col sm:flex-row justify-around m-5">
    <form on:submit={submitForm} class="flex flex-col sm:flex-row gap-3 items-center">
      {#if !submitted}
        <div>
          <label for="name" class="mr-2">Name</label>
          <input required="text" class="border-2 border-gray-300 p-1" id="name" bind:value={formData.name} />
        </div>
  
        <div>
          <label for="location" class="mr-2">Location</label>
          <select required class="border-2 border-gray-300 p-1" id="location" bind:value={formData.location}>
            <option value="">Select location</option>
            <option value="chennai">Chennai</option>
            <option value="bangalore">Bangalore</option>
            <option value="hyderabad">Hyderabad</option>
          </select>
        </div>
  
        <div>
          
          <input required type="checkbox" id="activeuser" bind:checked={formData.activeUser} />
          <label for="activeuser" class="mr-2">Active user</label>
        </div>
  
        <div>
          <label for="activeuser" class="mr-2">Date : </label>
          <input required class="border-2 border-gray-300 p-1" type="date" bind:value={formData.date} />
        </div>
  
        <button disabled={!formData.activeUser && !formData.date && !formData.name && !formData.location }
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
          >Submit</button>
      {:else}
        <p>Successfully submitted data!</p>
      {/if}
    </form>
  </div>
  
  
  
  