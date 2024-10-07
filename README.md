# NSLookup for DeveloperStar.com

This project is a simple **NSLookup** tool developed using **SvelteKit**. The tool allows users to query DNS records for a domain, specifically tailored for [DeveloperStar](https://developerstar.com/).

## Features
- Query DNS records including **A**, **MX**, **NS**, **TXT**, etc.
- User-friendly interface built with **SvelteKit**.
- Quick and reliable domain name server lookups.

## Technologies Used
- **SvelteKit**: Frontend framework for building user interfaces.
- **DNS-over-HTTPS (DoH)** API: For resolving DNS records securely.
- **JavaScript**: The core programming language for the app.
- **CSS**: Styling to make the application visually appealing.

## Getting Started
### Prerequisites
- **Node.js** (v16 or newer recommended)
- **npm** or **yarn** (package manager)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/NagareYash/NSLookup.git
   ```
2. Navigate to the project directory:
   ```bash
   cd NSLookup
   ```
3. Install dependencies:
   ```bash
   npm install
   ```

### Running the Development Server
To start the development server:
```bash
npm run dev
```
Visit [http://localhost:5173](http://localhost:5173) in your browser to see the NSLookup tool in action.

### Building for Production
To build the project for production:
```bash
npm run build
```

## Usage
Enter a domain (e.g., `developerstar.com`) into the input field and click **Lookup**. The application will return various DNS records, such as IP addresses (A records), mail servers (MX records), and more.

## Contributing
Feel free to fork the repository and submit pull requests. Contributions are welcome to improve features, fix bugs, or enhance the user experience.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Acknowledgements
- [SvelteKit Documentation](https://kit.svelte.dev/docs)
- [Google's DNS-over-HTTPS (DoH) API](https://developers.google.com/speed/public-dns/docs/doh)
