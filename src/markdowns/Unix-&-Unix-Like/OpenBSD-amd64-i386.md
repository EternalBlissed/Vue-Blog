# How to Install OpenBSD i386/amd64

## 1. Prepare Your ISO File on a CD/USB
- Use the `dd` command to prepare your installation media:

```bash
dd if=path_to_your_iso_file.iso of=/dev/sdX bs=4M status=progress
```

Replace `path_to_your_iso_file.iso` with the path to your ISO file and `/dev/sdX` with your CD/USB device.

## 2. Boot from Your CD/USB
- Access your BIOS/UEFI settings and select the CD/USB as the boot device.

## 3. Start Installation
- After booting, when prompted, select `(I)nstall` to start the installation process.

## 4. Keyboard Layout
- Select your keyboard layout. Type `L` to list all layouts or press Enter to use the default layout.

## 5. System Hostname
- Set your system hostname, e.g., `openbsd-box`.

## 6. Configure Network Interface
- To list all network interfaces, type `?`. For example, to use Ethernet on a Dell Latitude D505, type `fxp0`.

## 7. IPv4 Configuration
- Use `autoconf` to automatically configure the IPv4 address.

## 8. IPv6 Configuration (Optional)
- Optionally, use `autoconf` again for IPv6. This should configure DNS name servers automatically.

## 9. Root Password
- Set a secure password for the root account.

## 10. SSHD Configuration
- Enable or disable `sshd` as needed.

## 11. Xenodm Configuration
- Enable or Disable `xendodm`. (Preference: off)

## 12. Console Configuration
- Enable or Disable default console to `com0`. (Preference: off)

## 13. User Setup (Optional)
- Provide a username, e.g., `eternal`.
- Press Enter to use the same name for the full name.
- Set a secure password for this user.

## 14. Root SSH Login
- Enable or disable root SSH login. (Preference: off)

## 15. Timezone Configuration
- Set your timezone, e.g., `Australia/Sydney`.

## 16. Root Disk Selection
- Select the root disk for OpenBSD installation, e.g., `wd0`.

## 17. Disk Encryption
- Enable or disable root disk encryption. (Preference: on)

## 18. Disk Partitioning
- Use the whole disk and select the auto layout by pressing Enter.

## 19. Installation Sets
- Install the sets from your installation ISO. Select `no` if it's not mounted.
- Specify the installation media containing the sets, e.g., `sd0`.
- Press Enter to provide the default pathname.
- Follow prompts to select required sets or press Enter to use all. If prompted about a missing `SHA256.sig`, it's safe to continue by typing `yes`.

## 20. Final Steps
- The system will perform tasks like relinking to create a unique kernel.

## 21. Reboot
- Remove your installation media and press Enter to reboot.

## 22. Post-Installation Setup
- Once booted into your fresh install, log in with your user's name and password.
- To fix `doas` not working, become root with `su` and create a `doas` config at `/etc/doas.conf`, e.g., `permit :eternal`.
- Start the X server with `cwm` using `startx` or install your favorite programs with `doas pkg_add`.

## 23 Finish 
- Thats it! Have fun with your new OpenBSD system.

