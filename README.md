YouTube URL Fixer & Redirector
A lightweight, high-performance browser extension built on the modern Manifest V3 architecture. This extension optimizes user workflows on YouTube by sanitizing malformed URL prefixes and providing a seamless, one-click redirection mechanism to an alternative domain layer (yout-ube.com).

🚀 Key Features
URL Prefix Sanitization Dynamically monitors the browser address bar. If a YouTube video URL contains unexpected leading prefixes, the script cleanses the string and updates the browser history using state preservation APIs—without triggering a heavy page reload.

Dynamic DOM Injection Inserts a native, highly responsive Action Button (✨ Ir para Yout-ube) directly into the viewport layout strictly when a valid watch context (/watch?) is active.

SPA Lifecycle Compatibility Combines standard DOMContentLoaded execution, MutationObserver background trees, and a failsafe polling loop to handle YouTube's native Single Page Application (SPA) client-side routing seamlessly.

Zero Permissions Overhead Operates securely within explicit context limits without requiring invasive browser permission keys, ensuring maximum privacy and minimal resource footprints.

📂 Repository Architecture
Plaintext
├── manifest.json      # Extension configuration and permission scope
└── content.js         # Core content script managing URL mutations and DOM injection
🛠️ Installation Guide
Since this extension is in development, it can be loaded locally into any Chromium-based browser (such as Google Chrome, Brave, Microsoft Edge, or Opera):

1. Prerequisites
Download or clone this repository to your local machine.

Ensure both manifest.json and content.js are located in the same root folder.

2. Deployment Steps
Open your browser and navigate to the extensions management interface (e.g., chrome://extensions/).

Turn on Developer mode using the toggle switch in the upper right-hand corner.

Click the Load unpacked (Carregar expandida) button in the top left.

Select the local directory containing your project files.

💡 Result: The extension is now active and will automatically initialize upon visiting any valid YouTube video page.

⚙️ Mechanics & Implementation
Context Verification
The script evaluates the current global window location string against strict matching parameters before initializing the UI layer:

JavaScript
const searchStr = "youtube.com/watch?";
if (url.includes(searchStr)) {
    // Execution context confirmed
}
DOM Construction & Event Handling
The button layer is appended natively onto the document body object with an elevated z-index depth (99999) to guarantee visibility across varying YouTube player modes.

Clicking the element intercepts the video identifier string, shifts the core domain name to the target layout, and mutates window.location.href to execute the structural redirect safely:

JavaScript
btn.onclick = function() {
    const newURL = getModifiedURL();
    if (newURL) window.location.href = newURL;
};
📄 License
This project is intended for personal utility and development workflows. All modifications and code adaptations are free to be distributed under standard open-source conventions.
