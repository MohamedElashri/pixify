# **Pixify**

Pixify is a lightweight script to simplify batch image processing. The purpose is to strip metadata and distort photos slightly to increase privacy when sharing images online or with others.

---

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/MohamedElashri/pixify
   ```
2. Make the script executable:
   ```bash
   chmod +x pixify
   ```
3. Move it to a directory in your PATH for global access:
   ```bash
   mv pixify /usr/local/bin/
   ```

---

## **Usage**


### **Examples**

#### **Basic Usage**
To process all `.HEIC` files in the current directory:
```bash
pixify
```

#### **Specify Input and Output Directories**
Process images from a custom input folder and save them to a specific output folder:
```bash
pixify -i ./photos -o ./processed
```

#### **Process Specific Files**
Process specific `.HEIC` files in the input folder:
```bash
pixify -i ./photos -f IMG_1111.HEIC,IMG_2222.HEIC -o ./processed
```

#### **Adjust Quality and Resize**
Set JPEG quality to `85` and resize images to `92.5%` of their original size:
```bash
pixify -q 85 -r 92.5 -i ./photos -o ./processed
```

#### **Skip Metadata Backup**
To process images without saving metadata backups:
```bash
pixify -n -i ./photos -o ./processed
```

#### **View Help**
For detailed options:
```bash
pixify -h
```

---

### **Command Table**

| **Command**                | **Description**                                       | **Example**                                         |
|----------------------------|-------------------------------------------------------|---------------------------------------------------|
| `-i`, `--input`            | Specify the input directory containing `.HEIC` files. | `./pixify -i ./photos`                           |
| `-o`, `--output`           | Specify the output directory for processed images.    | `./pixify -i ./photos -o ./processed`            |
| `-q`, `--quality`          | Set the JPEG quality (default: `87`).                 | `./pixify -q 85 -i ./photos -o ./processed`      |
| `-r`, `--resize`           | Resize images by a percentage (default: `91`).        | `./pixify -r 92.5 -i ./photos -o ./processed`    |
| `-f`, `--files`            | Process specific files (comma-separated list).        | `./pixify -i ./photos -f IMG_1111.HEIC,IMG_2222.HEIC` |
| `-n`, `--no-backup`        | Skip metadata backup for processed images.            | `./pixify -n -i ./photos -o ./processed`         |
| `-h`, `--help`             | Display help message with all available options.      | `./pixify -h`                                    |

---


## **Dependencies**

- **ImageMagick**: For image processing.
- **ExifTool**: For metadata backup.

### Install on Debian/Ubuntu:
```bash
sudo apt update
sudo apt install imagemagick libimage-exiftool-perl
```

### Install on macOS (using Homebrew):
```bash
brew install imagemagick exiftool
```

---

## **License**

Pixify is licensed under the MIT License. See the `LICENSE` file for details.
