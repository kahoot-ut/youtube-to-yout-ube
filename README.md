<p align="center">
  <svg xmlns="https://filebin.net/2d3tk6mt9mntzdy6/youtube-logo-youtube-social-media-icon-free-png.ico" viewBox="0 0 24 24" width="120" height="120">
    <path fill="#FF1493" d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814z"/>
    <path fill="#FFFFFF" d="M9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
  </svg>
</p>
<h1 align="center">YouTube URL Fixer & Redirector</h1>

YouTube URL Fixer & Redirector
A lightweight, high-performance browser extension built on the modern Manifest V3 architecture. This extension optimizes user workflows on YouTube by sanitizing malformed URL prefixes and providing a seamless, one-click redirection mechanism to an alternative domain layer (yout-ube.com).

## 🚀 Key Features

*   **🔍 URL Prefix Sanitization**
    Dynamically monitors the browser address bar. If a YouTube video URL contains unexpected leading prefixes, the script cleanses the string and updates the browser history using state preservation APIs—without triggering a heavy page reload.
*   **✨ Dynamic DOM Injection**
    Inserts a native, highly responsive Action Button (`✨ Ir para Yout-ube`) directly into the viewport layout strictly when a valid watch context (`/watch?`) is active.
*   **🔄 SPA Lifecycle Compatibility**
    Combines standard `DOMContentLoaded` execution, `MutationObserver` background trees, and a failsafe polling loop to handle YouTube's native Single Page Application (SPA) client-side routing seamlessly.
*   **🛡️ Zero Permissions Overhead**
    Operates securely within explicit context limits without requiring invasive browser permission keys, ensuring maximum privacy and minimal resource footprints.

<!-- Badges para dar um visual profissional e dinâmico -->
![Manifest V3](https://img.shields.io/badge/Manifest-V3-blue?style=for-the-badge&logo=google-chrome&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=for-the-badge&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-orange?style=for-the-badge)

---## 📂 Repository Architecture

Organização limpa e direta dos arquivos do projeto:

```text
├── 📄 manifest.json   # Extension configuration and permission scope
└── ⚙️ content.js       # Core content script managing URL mutations and DOM injection
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
