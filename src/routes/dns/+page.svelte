
<script>
    import "../dns/page.css";

    // let domain = 'google.com';
    let apiKey = 'KU12jgqYtDQrcgGisbFIBA==yZb28JPkyU7DGR96'; // Replace with your API key
    let dnsTypes = ['A']; // DNS record types
    let results = [];
    let userInput = '';
  
    const fetchData = async () => {
      results = await Promise.all(
        dnsTypes.map(async (type) => {
          const response = await fetch(
            `https://api.api-ninjas.com/v1/dnslookup?domain=${userInput}&type=${type}`, // Use userInput
            {
              method: 'GET',
              headers: {
                'X-Api-Key': apiKey,
              },
            }
          );
  
          if (response.ok) {
            const data = await response.json();
            return { type, data };
          } else {
            return { type, error: `Error: ${response.status} - ${response.statusText}` };
          }
        })
      );
    };
  </script>
  <body>
    <nav class="bg-gray-800 py-6">
        <div class="container mx-auto">
          <div class="flex items-center justify-between">
            <div class="text-white text-2xl font-semibold pl-20">LOOKSMYDNS</div>
            <div class="space-x-4 pr-20">
              <a href="#" class="text-white px-11">Home</a>
              <a href="#" class="text-white px-11">About</a>
              <a href="#" class="text-white px-11">RoadMap</a>
              <a href="#" class="text-white px-11">Contact</a>
            </div>
          </div>
        </div>
      </nav>
  
  <div class="bg-gray-900 text-white min-h-screen flex flex-col justify-center items-center">
    <h1  class="text-6xl font-semibold mb-4">DNS Lookup</h1>
  
    <label for="domainInput">Enter Domain:</label>
    <input type="text" id="domainInput" bind:value={userInput} class="m-2 text-black	" />
  
    <button on:click={fetchData} class="bg-blue-500 text-white px-4 py-2 rounded">Fetch DNS Data</button>
  
    {#if results.length > 0}
      {#each results as { type, data, error }}
        <div>
          <h2>ALL Records</h2>
          {#if data}
            <pre>{JSON.stringify(data, null, 2)}</pre>
          {:else}
            <p>{error}</p>
          {/if}
        </div>
      {/each}
    {/if}
  </div>
  </body>
  

   <!-- src/routes/DnsLookup.svelte -->
<!-- src/routes/DnsLookup.svelte -->

  