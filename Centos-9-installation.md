# CentOS 9 Installation (GUI)

[Download CentOS 9 Stream ISO](https://mirror.stream.centos.org/9-stream/BaseOS/x86_64/iso/CentOS-Stream-9-20250210.0-x86_64-dvd1.iso)

---

### VirtualBox Setup

- Open VirtualBox and click **New**.
- ![image](https://github.com/user-attachments/assets/4010574f-3b26-4011-a4e9-a9bbde7b04f7)
 
  
- Set the name to **CentOS 9**, type to **Linux**, and version to **Red Hat (64-bit)**.
- ![image](https://github.com/user-attachments/assets/d00b7612-9b30-4e88-9786-288d714c0846)



  
- Allocate **4096 MB** RAM (According to requirement).  
  2 core CPU
  ![image](https://github.com/user-attachments/assets/71559668-16fc-4594-92be-e6e274dd01ab)
 
  
- Create a virtual disk:  
  - Select **VDI (Virtual Disk Image)**  
  - Choose **Dynamically allocated**  
  - Set **file location and size to 40 GB** (According to requirement)
  - ![image](https://github.com/user-attachments/assets/b2434416-0f17-4758-978a-b2d4eb1978cd)
  - ![image](https://github.com/user-attachments/assets/976a8c64-5200-49bb-b7b9-3af67936e283)




  
- Start the virtual machine,  
- ![image](https://github.com/user-attachments/assets/74141dc6-3982-453b-88bb-19957bf76d37)

- select the CentOS 9 ISO
- ![image](https://github.com/user-attachments/assets/09d61c84-fb26-45a5-be04-d7ed3f6f3318)

- and click **mount and reboot**
- ![image](https://github.com/user-attachments/assets/b208f35c-c864-4031-b017-699b4e7ce409)







---

## Installation

- Choose **Install CentOS 9**.
- ![image](https://github.com/user-attachments/assets/51bc9f60-c3d7-40a7-8491-917fe9e2854d)

 
- Select **English > English (India) > Continue**.
- ![image](https://github.com/user-attachments/assets/8bae1089-ce2b-4023-84a8-88e5995a32aa)


- Configure settings:  
  - **Date & Time**: Asia/Kolkata > Done  
  - **Keyboard Layout**: English (India, with rupee) > Add English (US) > Done  
  - **Language Support**: English (India) > Done
  - ![image](https://github.com/user-attachments/assets/1b8d4d16-588b-4771-bc97-0cd0bb64fe89)

  

- **Installation Source**: Verify ISO > Done  
  - Auto-Detect Media  
    Automatically detects bootable installation media (DVD, USB, ISO)  
  - Network Sources  
    Closest Mirror: Selects the fastest CentOS mirror  
    NFS: Installs from a shared network directory  
    HTTP/HTTPS: Fetches packages from online repositories via secure links  
    FTP: Downloads from an FTP server  
  - Custom Repositories  
    Allows specifying offline or private repositories for custom setups  
  - Manual Options  
    Change source, verify media, or fallback to network if no valid media is found  
  
  [for now select auto detect media]
  ![image](https://github.com/user-attachments/assets/d822d9c4-4834-439c-ac70-d6d587115f83)

  ![image](https://github.com/user-attachments/assets/bb5d0d4a-8cdb-4b36-a402-dd14c4abea7d)
 
  
- **Software Selection**: Select **Server with GUI**  
  - Base Environment Options:  
    These define the primary purpose of the system.  
    -  Server with GUI: Installs a server environment with a graphical user interface (GNOME)  
    -  Server: Provides a CLI-based server setup with essential services  
    -  Minimal Install: A lightweight installation with the bare minimum required to run CentOS  
    -  Workstation: For desktop use with a GUI and development tools  
    -  Custom Operating System: A fully customized setup to meet specific requirements  
    -  Virtualization Host: Configured to host and manage virtual machines  

  [for now select Server With GUI]

  - Additional Software for Selected Environment:  
    -  Each base environment includes optional add-ons to enhance functionality  
    -  Examples:  
      -  Development Tools: Compiler and libraries  
      -  Web Server: Apache, Nginx  
      -  File Server: Samba, NFS utilities  
      -  System Administration Tools: Diagnostic and monitoring tools  
  
  [for now don't select anything]
  ![image](https://github.com/user-attachments/assets/e4236616-ef60-4d69-8820-a5eca429d030)
  ![image](https://github.com/user-attachments/assets/a74b1eb9-43b8-4850-94e8-ed0109f9bf5f)


 

- Installation Destination
- ![image](https://github.com/user-attachments/assets/f4aea9c9-f85a-4172-89a3-1c59a6e9c573)

  
  - **Custom partitioning** > Done  
  - Create partitions:  
    - `/boot` - **1024 MiB**, **ext4**, Standard  
    - `swap` - **4096 MiB**, Standard  
    - `/` - **XFS file system**, Standard  
  - Click **Done > Accept Changes**

  Selecting the Installation Device  
  When you reach the Installation Destination screen:  
  - Local Standard Disks:  
    -  Displays the available storage devices (e.g., HDD, SSD)  
    -  Select the disk where CentOS will be installed by clicking the checkbox next to it  
  - Specialized Storage Devices (optional):  
    -  Used for network-attached storage (NAS) or advanced configurations like iSCSI

  Storage Configuration Options  
  After selecting a device, choose a storage configuration mode:  
  a) Automatic Partitioning  
    - The installer automatically creates default partitions:  
      -  /boot (for bootloader files)  
      -  swap (used for virtual memory)  
      -  / (root directory for the OS)  
    - Suitable for beginners or general-purpose installations
  
  b) Custom Partitioning  
    - Provides full control over partitioning, allowing manual definition of partitions and their sizes  
    - Steps:  
      1. Partition Scheme:  
         § Standard Partition: Traditional partitioning (no LVM)  
         § LVM (Logical Volume Manager): Allows resizing, snapshots  
         § LVM Thin Provisioning: Dynamically allocates storage  
      2. Create Partitions:  
         § Recommended scheme:  
           -  /boot → 1 GB (Standard Partition)  
           -  swap → 4 GB (Standard Partition)  
           -  / → Remaining space (Standard Partition)  
           -  File System: ext4 or XFS  
      3. Encrypt My Data:  
         § Option to encrypt partitions for security  
      4. Additional Space:  
         § Reclaim space from existing partitions if needed
  ![image](https://github.com/user-attachments/assets/3e0b4162-845f-43f4-8b27-259948e796d9)
  ![image](https://github.com/user-attachments/assets/aa373c53-02f6-4425-9009-f92c25bcfc66)
  ![image](https://github.com/user-attachments/assets/558aa6ce-38f2-41aa-8827-7fb3ef07cdef)
  ![image](https://github.com/user-attachments/assets/276942a8-29d5-4bd4-8a11-0be2d6972181)


 
  Partition Details  
  /boot Partition  
  - Purpose: Stores bootloader files  

  swap Partition  
  - Purpose: Virtual memory when physical RAM is fully used  

  / (root) Partition  
  - Purpose: Main directory containing the OS and user files  

- **KDUMP**: No changes  
  Purpose: Configure KDUMP for kernel crash dumping  
  Features:  
  Enable/disable KDUMP  
  Specify memory allocation for crash dumps  
  [for now Keep it Enabled]

- **Network & Hostname**:  
  - Enable **enp0s3**  
  - Configure IPv4 manually, disable IPv6, save settings  
  - Set hostname to **Demo**
  - ![image](https://github.com/user-attachments/assets/52f31fba-f00a-4c35-9f77-7f9ad3923179)

  
- **Security Policy**: No changes  
  Purpose: Apply predefined security policies to the system  
  Features:  
  Choose profiles like CIS or DISA STIG  
  Integrate system-wide security hardening  
  [for now Keep it disabled]

- 9. Set **root password** and create a user:  
  - Full name: `<demouser>`  
  - Username: `<demouser>`  
  - Tick **Make this user administrator**
  - ![image](https://github.com/user-attachments/assets/2d8e2c4c-67aa-4bd1-81ca-094b82836d8b)
  - ![image](https://github.com/user-attachments/assets/982fb8f2-dcd7-4a19-9ed2-67b0de06ea6d)



  

  Lock the Root Account [for now Keep it disabled]  
  - Purpose:  
    -  Prevents the root account from being used directly for login  
    -  The root account remains available but can only be accessed through sudo

  Allow Root SSH Login with Password [for now Keep it enabled]  
  - Purpose:  
    -  Enables the root user to log in remotely via SSH using a password

  - User Creation  
    Create a non-root user for daily use
    

[click begin installation]
![image](https://github.com/user-attachments/assets/3fb14014-7dcc-4b27-bdf7-3c81ffff9a9d)



