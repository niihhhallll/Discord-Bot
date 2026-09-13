# 🚀 Discord Webhook C++ Library

A lightweight, high-performance C++ library designed to send messages, rich embeds, photos, videos, and file attachments to Discord servers in **under 5 lines of code**.

![Build Status](https://img.shields.io/badge/status-in--development-yellow.svg)
![Language](https://img.shields.io/badge/language-C%2B%2B11-blue.svg)
![Dependencies](https://img.shields.io/badge/dependencies-libcurl-green.svg)
![License](https://img.shields.io/badge/license-MIT-informational.svg)

> ⚠️ **Project Status:** This library is currently **under active development**. Core features are functional, but API signatures may change or contain bugs. Bug reports, feature suggestions, and pull requests are highly appreciated!

---

## 🌟 Overview

The **Discord Webhook C++ Library** provides a clean, native C++ interface to interact with Discord's Webhook API without forcing developers to drag in massive HTTP or JSON frameworks. 

Whether you are building game engine telemetry, automated logging systems, server monitoring utilities, or real-time notification alerts, this library enables multi-part file uploads and rich messaging with minimal setup and near-zero memory footprint.

---

## ⚡ Quick Start

Send a complete payload with a message and media attachment in **under 5 lines of code**:

```cpp
#include "../include/send.h"

int main() {
    MsgDetails Msg1;
    std::string Hook = "Your Discord WebHook"; 
    WebHook Send(Hook,&Msg1);
    std::string h = "Your Message"; 
    std::string* msg = &h; 
    Msg1.SetMessage(msg);
    Send.sendMessage();
    std::string f = "/File/Path/To/Your/File";  
    Msg1.FilePath = &f; 
    Send.sendFile(); 
    return 0; 
}
```

---

## ✨ Features

- **⚡ Minimalistic API:** Full-featured Discord integration with sub-5 lines of code.
- **📦 Zero Heavy Dependencies:** Built on native C++ and standard `libcurl` to avoid third-party bloat.
- **🚀 High Performance:** Native C++ execution ensures zero unnecessary dynamic allocations and fast payload delivery.
- **🖼️ Full Media & File Support:** Effortlessly upload images, videos, logs, and arbitrary file attachments.
- **🎨 Rich Embed Support:** Construct structured embeds with custom titles, descriptions, colors, and fields.
- **🛠️ Cross-Platform Build System:** Managed via CMake for easy compilation on Linux, macOS, and Windows.

---

## 🛠️ How to Run It Locally

Follow these step-by-step instructions to compile and test the example application on your system.

### 1. Prerequisites

Ensure your system has the following installed:
- **C++ Compiler:** GCC, Clang (supporting C++11 or higher)
- **CMake:** Version 3.10 or higher
- **libcurl:** System HTTP library (`libcurl4-openssl-dev` on Debian/Ubuntu)

### 2. Configuration

Navigate to the project directory and open `src/main.cpp` using your preferred text editor:

```bash
cd Discord-Bot/src

# Open with VS Code:
code main.cpp

# Or open with Vim / Neovim:
vim main.cpp
```

Inside `src/main.cpp`, configure your target Discord Webhook URL, message content, and attachment paths:

```cpp
#include "DiscordWebhook.h"

int main() {
    // Replace with your real webhook URL
    MsgDetails Msg1;
    std::string Hook = "Your Discord WebHook"; 
    WebHook Send(Hook,&Msg1);
    std::string h = "Your Message"; 
    std::string* msg = &h; 
    Msg1.SetMessage(msg);
    Send.sendMessage();
    std::string f = "/File/Path/To/Your/File";  
    Msg1.FilePath = &f; 
    Send.sendFile(); 
    return 0; 
}
```

### 3. Compilation & Build

Return to the root project directory, enter the `build` directory, and compile using CMake and Make:

```bash
# Return to the root directory
cd ..

# Enter the build folder
cd build

# Generate Makefiles
cmake ..

# Compile the application
make
```

### 4. Run the Binary

After a successful build, run the generated `Send` executable:

```bash
./Send
```

🎉 **Success!** Your message and file attachment will instantly appear in your configured Discord channel.

---

## 📁 Project Directory Structure

```text
Discord-Bot/
├── build/                 # Compiled binaries and CMake build cache
├── include/               # Public library headers
│   └── send.h             # Core library header file
├── src/                   # Source code and demo entry point
│   ├── send.cpp # Library implementation
│   └── main.cpp           # Demo executable source code
├── CMakeLists.txt         # Build configuration script
├── LICENSE                # License information
└── README.md              # Project documentation
```

---

## ⚙️ How It Works

Many Discord integration libraries rely on massive external dependencies like heavy JSON parser trees and web framework wrappers. 

This library takes a minimalist approach:
1. **Direct HTTP Communications:** Communicates directly with Discord's REST API using `libcurl`.
2. **Multipart/Form-Data Handling:** Constructs native HTTP `multipart/form-data` requests to seamlessly bundle JSON payloads and binary file streams into a single connection round-trip.
3. **Performance First:** Low memory allocations and low runtime overhead, making it ideal for games, embedded systems, and resource-constrained application logging.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more details.

---

## 🙏 Credits & Acknowledgements

- Powered by [libcurl](https://curl.se/libcurl/) for robust HTTP network requests.
- Inspired by the official [Discord Webhook API Documentation](https://discord.com/developers/docs/resources/webhook).
