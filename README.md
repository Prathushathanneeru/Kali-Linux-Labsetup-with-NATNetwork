# Kali-Linux-Labsetup-with-NAT-Network
The labsetup for kali linux in your windows laptop with VMware a virtual envirement to operate a kali linux and access to sharable folders/files from windows to virtual machine. 
# Steps to Follow

## 1. Download and install 7-Zip

Download: [7-zip.org](https://7-zip.org/download.html)

7-Zip is a free, open-source file archiver and compressor utility for Windows.

## 2. Download and install VMware on your laptop

Download: [VMware Workstation](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)

VMware creates a virtual environment that lets you run other operating systems without disturbing your laptop's Windows OS.

## 3. Configure the network settings in VMware (create a NAT network in 10.0.0.0/24)

1. Open **VMware Workstation**, then go to **Edit → Virtual Network Editor**.
2. Click **Change Settings** (bottom right, admin rights needed).
3. Select **VMnet8** (type NAT). If it is missing, click **Add Network → VMnet8**.
4. Set the following:
   - **Type:** NAT
   - **Subnet IP:** `10.0.0.0`
   - **Subnet mask:** `255.255.255.0`
5. Click **NAT Settings** and change the **Gateway IP** to `10.0.0.254`, then click **OK**.
   > Recommended: `10.0.0.254`, because the host's VMnet8 adapter often takes `.1`.
6. Click **DHCP Settings** and set the range to `10.0.0.100` – `10.0.0.200`, so DHCP never hands out the gateway or host addresses.
7. Click **Apply → OK**.

## 4. Download and import the Kali Linux virtual machine into VMware

Download: [kali.org/get-kali](https://kali.org/get-kali)

After importing and installing Kali Linux in VMware, follow these steps to share files:

1. Open **Network** settings in Kali.
2. Click **IPv4 Settings** and enter the same IP details you set for the NAT network:
   - **Gateway:** `10.0.0.254`
   - **Netmask:** `255.255.255.0`
3. Set **DNS** to `8.8.8.8`, then click **OK**.

<img width="1917" height="902" alt="image" src="https://github.com/user-attachments/assets/518e0927-2111-4e2b-a1e6-14f7b0e18976" />
<img width="1080" height="677" alt="image" src="https://github.com/user-attachments/assets/82581aec-bc47-45af-b80c-7c1d0eac44fa" />

## The files and folders can be sharable from your WindowsOS to the Kali Linux Operating System. 


<img width="1715" height="795" alt="image" src="https://github.com/user-attachments/assets/70208ac3-d88d-433e-8269-c5e1ccb1dbe4" />



