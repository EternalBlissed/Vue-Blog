# Installing Packages on Slackware

Installing programs on Slackware Linux differs from more modern distributions. Here's a comprehensive guide.

## 1. Using Slackpkg (Recommended for Beginners)
`slackpkg` is a network-based package management tool.

### Steps:
- **Configure Mirrors:**
  - Edit `/etc/slackpkg/mirrors`.
  - Uncomment a mirror close to your location.

- **Update Package List:**
  ```
  slackpkg update
  ```

- **Search for a Package:**
  ```
  slackpkg search [package_name]
  ```

- **Install a Package:**
  ```
  slackpkg install [package_name]
  ```

## 2. Using SlackBuilds (For More Control)
SlackBuilds are scripts for compiling and installing packages from source.

### Steps:
- **Visit SlackBuilds.org:**
  - Find and download the script and source.

- **Extract and Run the SlackBuild Script:**
  ```
  tar xvf [package_name].tar.gz
  cd [package_name]
  ./[package_name].SlackBuild
  ```
  - This compiles and creates a `.tgz` package.

- **Install the Compiled Package:**
  ```
  installpkg /tmp/[package_name]*.tgz
  ```

## 3. Using Third-Party Repositories:
Third-party repositories like SlackBuilds.org and Alien Bob's Repo offer additional packages.

## 4. Manual Installation:
For software not available via other methods, you can compile manually.

### Steps:
- **Download the Source Code:**
  - Usually from the official website.

- **Extract the Source:**
  ```
  tar xvf [source_archive].tar.gz
  ```

- **Compile and Install:**
  ```
  cd [extracted_folder]
  ./configure
  make
  sudo make install
  ```

## 5. Tips:
- Read `README` or `INSTALL` files in source directories.
- Keep your system updated with `slackpkg upgrade-all`.
- Consider SlackBuilds for controlled software management.

## 6. Post-Installation:
- Check for additional dependencies and follow any software-specific post-installation instructions.

## Conclusion:
Slackware's package management ensures control and understanding of your system, adhering to its philosophy of simplicity and full control.

---

