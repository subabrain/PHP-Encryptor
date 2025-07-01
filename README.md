# 🔒 PHP Encryptor Suite

A complete solution for protecting your PHP scripts:
- **Encrypt** your code with a modern Qt desktop app (GUI & CLI, Windows)
- **Decrypt & execute** at runtime with a PHP extension (Windows)

![grafik](https://github.com/user-attachments/assets/a4cba82c-4a96-4d2d-9ddf-2e10823bbf5b)


## 🚀 Quick Start

1. **Encrypt your PHP script** using the Qt Encryptor App (GUI or CLI)
2. **Deploy the encrypted files** and the PHP Extension to your server
3. **Run the encrypted script** via the PHP extension in your PHP code



## 🖥️ 1. Qt Encryptor App

![grafik](https://github.com/user-attachments/assets/d84c37bb-ac5c-4744-b1aa-87d8a0f60365)


**Encrypt your PHP files with or without a graphical interface.**

### GUI Mode

- **Windows:** Double-click `php_encryptor.exe`
- **Linux:** Run `./php_encryptor` in the terminal (may require `chmod +x`)

**Fill in:**
- **PHP Script:** Your source `.php` file
- **Encrypted Output File:** Where the encrypted PHP goes
- **Encrypted Key File:** Where your encrypted user key is saved
- **User Key:** Your password/key (8–32 characters)

**Click:** **Encrypt PHP File**  
You will get two files:  
- `encrypted_php.bin`  
- `encrypted_key.bin`

### CLI Mode

```sh
# Windows
php_encryptor.exe input.php encrypted_php.bin encrypted_key.bin "mySecretKey"
```

## 🧩 2. Using the PHP Extension

The included **PHP extension** (`php_encryptor_extension.dll`) allows you to securely decrypt and run your encrypted PHP scripts at runtime.

### 📥 Installation

This Version is compiled for PHP 8.0.11 (Windows NTS - other OS/Versions will follow) - you can grab it here: 
https://windows.php.net/downloads/releases/archives/php-8.0.11-nts-Win32-vs16-x64.zip

1. **Copy the required files:**
    - `phpcpp.dll`  
    into your PHP directory where your `php.exe` is stored. You can find them in this repository.

    Then copy  
    - `php_encryptor_extension.dll`  
    into your PHP `ext/` folder.

2. **Edit your `php.ini`:**

    Add the following line:
    ```ini
    extension=extension_encrypt
    ```
    And change the extension directory
   ```ini
    ; On windows:
    extension_dir = "ext"
    ```

    > **Note:**  
    > - Make sure that `phpcpp.dll` are either in the same directory as your `php.exe` or available in your system `PATH`.  
    > - The DLLs must match your PHP’s architecture (here x64).
    > - The extension filename in php.ini **should not** include `.dll` or `.so` on Windows (just `extension=extension_encrypt`).

4. **Restart your web server** or the PHP process (if running as a service).


### 📝 Usage in PHP

After installing the extension, decrypt and run your encrypted script with:

```php
<?php
decrypt_and_eval("encrypted_php.bin", "encrypted_key.bin");
?>
