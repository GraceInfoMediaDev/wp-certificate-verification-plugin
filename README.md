# WordPress Certificate Verifier

A lightweight, Object-Oriented Programming (OOP) based WordPress plugin that allows users to verify student or participant certificates instantly using their unique roll numbers.

## Features

- **Modern OOP Architecture:** Fully written using modern PHP classes and clean, modular methods.
- **Fast Performance:** Uses direct server file-checking via `file_exists()` instead of heavy directories loops.
- **Secure Handling:** Built-in protection against cross-site scripting (XSS) and cross-site request forgery (CSRF) via WordPress nonces and sanitisation.
- **Case-Insensitive Searching:** Automatically handles formatting mismatches if users enter uppercase or lowercase values.
- **Modern Responsive UI:** Features a beautifully styled input form card built directly with clean CSS.

## Installation

1. Download or clone this repository as a `.zip` file.
2. Go to your WordPress Dashboard -> **Plugins** -> **Add New Plugin**.
3. Click **Upload Plugin**, choose the downloaded file, and click **Install Now**.
4. Click **Activate Plugin**.

## Directory Structure & Configuration

For the verification system to work, you must store your certificate images directly inside the plugin's folder on your server using FTP or your hosting provider's File Manager.

Set up your files according to the following layout:

```text
wp-content/plugins/wp-certificate-verifier/
├── wp-certificate-verifier.php  (The plugin file)
└── your-certificates/           (Folder - Create this if missing)
    ├── dic-7861301.jpg          (Keep image names lowercase)
    └── dic-1234567.jpg
```

*Note: Ensure all image names inside `your-certificates/` are formatted in **lowercase** and saved with a `.jpg` extension.*

## Usage

Simply paste this shortcode onto any WordPress page, post, or widget area where you want the certificate search widget to display:

```text
[gim_certificate_verifier]
```

### How it Works

1. The user visits the webpage and encounters a styled registration card panel.
2. The user types their roll number (e.g., `DIC-7861301`) and hits **Submit**.
3. The plugin trims whitespace, checks the directory, and instantly embeds the matching certificate on the webpage if found.
4. If the certificate path does not exist, an error notification stating *"It is not matched in our records."* gracefully alerts the user.

## Requirements

- WordPress 5.0 or higher
- PHP 7.4 or higher

## License

This project is licensed under the MIT License - feel free to modify and use it for personal or commercial projects.