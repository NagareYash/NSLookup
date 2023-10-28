<!-- src/DnsLookup.svelte -->
<script>
  import { onMount } from 'svelte';

  let domain = 'google.com';
  let recordType = 'A'; // Default to 'A' record type
  let result = '';

  const recordTypes = [
    'A',
    'AAAA',
    'MX',
    'CNAME',
    'TXT',
    'AFSDB',
    'APL',
    'CAA',
    'CDS',
    'CERT',
    'CSYNC',
    'DHCID',
    'DLV',
    'DNAME',
    'DS',
    'HINFO',
    'HIP',
    'SECKEY',
    'IXFR',
    'KEY',
    'KX',
    'LOC',
    'MX',
    'NAPTR',
    'NS',
    'NSEC',
    'NSEC3',
    'NSEC3PARAM',
    'OPENPGPKEY',
    'OPT',
    'PTR',
    'RP',
    'RRSIG',
    'SIG',
    'SMIMEA',
    'SOA',
    'SRV',
    'SSHFP',
    'TA',
    'TKEY'


    // Add more record types as needed
  ];

  const performLookup = async () => {
    try {
      const response = await fetch(`https://dns-lookup5.p.rapidapi.com/simple?domain=${domain}&recordType=${recordType}`, {
        method: 'GET',
        headers: {
          'X-RapidAPI-Key': 'df966717d5msh8da63f660e16a31p1f1f82jsn6902dbc06d25',
          'X-RapidAPI-Host': 'dns-lookup5.p.rapidapi.com'
        }
      });

      if (!response.ok) {
        throw new Error(`HTTP Error: ${response.status}`);
      }

      const data = await response.text();
      result = data;
    } catch (error) {
      console.error(error);
      result = 'Error: Unable to fetch DNS records. Please check your input and try again.';
    }
  };
</script>

<main>
  <h1>DNS Lookup</h1>
  <div>
    <label for="domain">Domain:</label>
    <input type="text" id="domain" bind:value={domain} />
  </div>
  <div>
    <label for="recordType">Record Type:</label>
    <select id="recordType" bind:value={recordType}>
      {#each recordTypes as type}
        <option value={type}>{type}</option>
      {/each}
    </select>
  </div>
  <button on:click={performLookup}>Lookup</button>
  <div>
    <pre>{result}</pre>
  </div>
</main>

<style>
  /* Add your CSS styles here if needed */
</style>
