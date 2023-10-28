<script>
  import "../app.css";
  import Icon from '@iconify/svelte';
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
  <div
    class="bg-gray-900 text-white min-h-screen flex flex-col justify-center items-center"
  >
    <div class="text-center">
      <h1 class="text-6xl font-semibold mb-4">NSLOOKUP</h1>
      <p class="text-lg mb-8 px-44">
        Welcome to <span class="text-2xl font-semibold">NSLookup Online</span>,
        your trusted tool for querying
        <span class="text-2xl font-semibold">DNS</span>
        records. <br />
        NSLookup is a Website
        <span class="text-2xl font-semibold">DNS(Domain Name System)</span>
        lookup tool that provides quick and accurte information about domain
        names and IP addresses. <br> Whether you're troubleshooting network issues,
        verifying DNS records, or simplify exploring the intricacies of the
        internet's addressing system,
        <span class="text-2xl font-semibold"> NSLookup</span> is your go-to
        resource. <br>  Enter a
        <span class="text-2xl font-semibold">domain name</span>
        or <span class="text-2xl font-semibold">domain name</span> , click
        <span class="text-2xl font-semibold">'Lookup'</span> and unlock valuable
        insights into the world of DNS.'
      </p>
    </div>
    <a href="/dns"
        ><button class="bg-blue-500 decoration-gray-50 px-4 py-2 rounded"
          >
    <div class="bg-gray-800 p-6 rounded-lg text-center flex">
      <Icon icon="tabler:network" color="" width="60" height="50"  />
      <h2 class="text-3xl font-semibold mb-4 pr-4">DNS LOOKUP</h2>
      </button></a>
    
  </div>
</body>
<slot />
