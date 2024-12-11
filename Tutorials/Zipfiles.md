<img src="../assets/zip-file-format.png" alt="Alt Text" width="400">


# Comprehensive Guide to Managing Compressed Files

Compressed files are widely used for archiving, storing, and sharing data more efficiently. Different file formats offer various levels of compression and features. This guide will help you understand how to handle these files in Linux and Windows environments.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Common Compressed File Types](#common-compressed-file-types)
- [Managing Compressed Files in Linux](#managing-compressed-files-in-linux)
  - [.zip Files](#zip-files)
  - [.7z Files](#7z-files)
  - [.tar.gz Files](#targz-files)
  - [.tar.bz2 Files](#tarbz2-files)
  - [.gz Files](#gz-files)
  - [.bz2 Files](#bz2-files)
- [Managing Compressed Files in Windows](#managing-compressed-files-in-windows)
  - [7-Zip for Various Formats](#7-zip-for-various-formats)
- [Additional Tips](#additional-tips)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Compressed files reduce storage space and make data transfer more efficient. This guide covers common file formats, their usage, and methods for managing them on Linux and Windows systems.

<br>

## **Common Compressed File Types**

1. **.zip**: Widely used format, supported natively by many operating systems.
2. **.7z (7-Zip)**: Known for high compression ratio, uses LZMA and LZMA2 compression.
3. **.rar**: Commonly used for high compression, proprietary format.
4. **.tar**: Archive format, often used with compression formats like gzip or bzip2.
5. **.tar.gz (.tgz)**: TAR archive compressed with gzip.
6. **.tar.bz2 (.tbz, .tbz2)**: TAR archive compressed with bzip2.
7. **.gz**: Compressed with gzip, usually single files.
8. **.bz2**: Compressed with bzip2, usually single files.

<br>

## **Managing Compressed Files in Linux**

### **.zip Files**

- **To Extract**:

  ```bash
  unzip filename.zip
  ```

- **To Create**:

  ```bash
  zip -r archive_name.zip folder_or_file_to_compress
  ```

<br>

### **.7z Files**

- Requires `p7zip` package.
- **To Extract**:

  ```bash
  7z x filename.7z
  ```

- **To Create**:

  ```bash
  7z a archive_name.7z folder_or_file_to_compress
  ```

<br>

### **.tar.gz Files**

- **To Extract**:

  ```bash
  tar -xzvf filename.tar.gz
  ```

- **To Create**:

  ```bash
  tar -czvf archive_name.tar.gz folder_or_file_to_compress
  ```

<br>

### **.tar.bz2 Files**

- **To Extract**:

  ```bash
  tar -xjvf filename.tar.bz2
  ```

- **To Create**:

  ```bash
  tar -cjvf archive_name.tar.bz2 folder_or_file_to_compress
  ```

<br>

### **.gz Files**

- **To Extract**:

  ```bash
  gunzip filename.gz
  ```

- **To Create** (for single files):

  ```bash
  gzip filename
  ```

<br>

### **.bz2 Files**

- **To Extract**:

  ```bash
  bunzip2 filename.bz2
  ```

- **To Create** (for single files):

  ```bash
  bzip2 filename
  ```

<br>

## **Managing Compressed Files in Windows**

### **7-Zip for Various Formats**

- **7-Zip Installation**:
  Download and install from [7-Zip's official website](https://www.7-zip.org/).

- **To Extract (General)**:
  Right-click the file → 7-Zip → Extract Here.

- **To Create (General)**:
  Right-click the folder/file → 7-Zip → Add to archive.

<br>

## **Additional Tips**

- **Choosing Format**:
  Consider the level of compression needed and the software available to your audience. `.zip` is universal but may not offer the best compression.

- **Secure Compression**:
  Some formats like `.7z` support password encryption for added security.

- **Large Files**:
  For very large archives, consider using a format that supports multi-part archives, like `.7z` or `.rar`.

<br>

## **Resources**

- [7-Zip Official Website](https://www.7-zip.org/)
- [GNU tar Documentation](https://www.gnu.org/software/tar/)
- [gzip Manual](https://www.gnu.org/software/gzip/manual/gzip.html)

<br>

## **Contribution**

Your contributions can make these scripts even better:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.

- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/09/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
