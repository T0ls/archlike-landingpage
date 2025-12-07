# Archlike Landing Page — Hyprland Terminal

[![Live demo](https://img.shields.io/badge/demo-live-brightgreen?style=for-the-badge)](https://T0ls.github.io/archlike-landingpage)
[![License: MIT](https://img.shields.io/badge/License-MIT-0a66ff?style=for-the-badge)](https://creativecommons.org/licenses/by/4.0/)
[![Made with HTML5 & CSS3](https://img.shields.io/badge/made%20with-HTML5%20%26%20CSS3-e34f26?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
[![Style: Hyprland](https://img.shields.io/badge/style-Hyprland-1793d1?style=for-the-badge)](https://hyprland.org/)

A **terminal-style landing page** simulating an Arch Linux desktop environment with the Hyprland window manager. The project recreates the command-line boot experience, complete with fluid animations, simulated "fastfetch" output, and an interactive SSH login sequence.

> Just clone, edit the config, and feel the ricing power.

---

## Why this repo?

A friend of mine needed a creative landing page for his NAS (Network Attached Storage).
So i designe a landing page that reflected a passion for **"ricing"** and Unix-like systems. Instead of a standard landing page, this page welcomes the user with a familiar terminal interface, simulating the aesthetic of a floating window in Hyprland with transparency, borders, and smooth animations, making navigation an immersive experience.

---

## Main features

- **Hyprland Simulations**: Entry/exit animations (`hypr-pop`, `hypr-out`) and window styling that perfectly mimics a modern Wayland compositor.
- **Fake Fastfetch**: Dynamically generates system specs (CPU, GPU, Memory, Uptime) to simulate a real Arch Linux environment.
- **SSH Sequence**: An automated boot sequence simulating SSH command typing and remote server connection.
- **Interactive Shell**: An interactive prompt that accepts keyboard commands (desktop) or button inputs (mobile).
- **Responsive Design**: Optimized for all devices. On mobile, the input prompt is replaced by touch-friendly buttons, and the fastfetch layout adapts vertically.
- **No Dependencies**: Written entirely in **Vanilla JS, HTML, and CSS**. No frameworks, lightweight, and fast.

---

## Quick setup

1.  **Clone** the repository.
2.  **Configuration**:
    No build step required. Open `index.html` directly and edit the `CONFIG` constant inside the `<script>` tag to customize the displayed data:
    ```javascript
    const CONFIG = {
        ip: '81.57.121.143', // Your simulated IP
        port: '54269',
        fastfetch: {
            OS: 'Arch Linux x86_64',
            Host: 'your-host-name',
            // ... edit hardware and stats here
        }
    };
    ```
   
3.  **Run**: Open `index.html` in your browser or deploy to GitHub Pages.

---

## Interactions & UI

- **Boot Sequence**: On load, the window appears with a pop-up animation, renders the fastfetch output, and starts the simulated SSH connection.
- **Command Line**:
    - Type the number or name of an option (e.g., "1", "qbt", "files") and press Enter.
    - The terminal supports backspace and realistic text input.
- **Mobile Mode**:
    - On small screens (<700px), the text prompt is hidden.
    - Clickable buttons for menu options appear automatically.
- **Virtual Keyboard**: On tablets and larger touch devices, a hidden input handles virtual keyboard activation.

---

## Customization

**Menu & Links**
The navigation system is modular. You can add new links by modifying the `MENU` array in the script:
```javascript
const MENU = [
    { 
      id: 'new-link', 
      label: 'My Blog', 
      path: 'blog.html', 
      aliases: ['3', 'blog', 'b'] 
    },
    // ...
];
