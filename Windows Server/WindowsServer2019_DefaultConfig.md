# Windows 2019 Server Config

>This guide will walk you through the process of cloning a Windows 2019 Server from a VMware vmdk template, configuring the network properties of the server, adding it to the domain, and activating its license via KMS.

## Creating Windows 2019 Server

1. Open the VMware vSphere client and log in to the vCenter server.

2. Navigate to the virtual machine inventory and open the `Template folder`.

3. Right-click the template and select `clone to Virtual Machine`.

4. In the server Virtual Machine wizard, provide a name for the new server, select the data center and folder location where you want to create the server, and click Next.

5. Select the ESXi host or cluster where you want to place the server and click Next.g

6. Select the storage location where you want to store the server's virtual disk files and click Next.

7. Choose the virtual disk format for the server(**its recommended to leave it the same as source**) and click Next.

8. Review the server settings and click Finish to start the cloning process.

9. Wait for the cloning process to complete, which may take some time depending on the size of the virtual machine.

## Configuring the network properties of the server

1. Power on the serverd virtual machine.

2. Log in to the Windows 2019 Server using an account with administrative privileges. **Reference Systems Password List**

3. Configue the IP address, subnet mask, and default gateway, DNS server addressesfor the network.

4. Reboot server.

## Adding the server to the domain

1. Press `Windows + R` keys together, type the command `sysdm.cpl` in the Run dialog box and press Enter. Alternatively, you can open Command Prompt and type the same command to open System Properties.

2. Click on the Change settings link next to `To rename this computer or change its domain or workgroup`, click Change.

3. Click the `Change` button to join the computer to a domain.

4. Enter the name of the domain and click OK.

5. Enter the credentials of an account that has permissions to join computers to the domain and click OK.

6. Wait for the computer to join the domain and reboot.

## Activating the Windows 2019 Server license via KMS

1. Open the `Server Manager` console.

2. Select `Local Server`, click `Not Activated` button beside theProduct ID and enter the `GVLK key` **located inside the Reference Systems Password List**.

3. Wait for the activation to finish the and reboot.
