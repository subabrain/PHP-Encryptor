## 🧩 Using the PHP Extension

![grafik](https://github.com/user-attachments/assets/ed213f9b-8f32-42a1-81d1-d4b69a25e91d)

The included **PHP extension** (`php_encryptor_extension.dll`) allows you to securely decrypt and run your encrypted PHP scripts at runtime.



### 📥 Installation

1. **Copy the files:**
    - `phpcpp.dll`  
    - `libcrypto-1_1-x64.dll`  
    - `libssl-1_1-x64.dll`  
    into your PHP directory where your php.exe is stored. You can find them in this Repository.
    Now copy these File `php_encryptor_extension.dll` from this repository into the PHP ext/ folder.

2. **Edit your `php.ini`:**

    Add the following line:
    ```ini
    extension=extension_encrypt
    ```

    > **Note:**  
    > - Make sure that `phpcpp.dll`, `libcrypto-1_1-x64.dll`, and `libssl-1_1-x64.dll` are either in the same directory as your `php.exe` or available in your system `PATH`.  
    > - The DLLs must match your PHP’s architecture (here x64).

3. **Restart your web server** or the PHP process (if running as a service).

### 📝 Usage in PHP

![grafik](https://github.com/user-attachments/assets/b3dbb2a3-01c0-4644-bfe2-f18d05e9da03)


After installing the extension, decrypt and run your encrypted script with:

```php
<?php
decrypt_and_eval("encrypted_php.bin", "encrypted_key.bin");
?>
```

### Important

Now you can use encrypted php files :)

Use this at your own Risk!
