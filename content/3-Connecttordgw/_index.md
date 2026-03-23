---
title : "Connecting to RDGW"
date : 2024-01-24T00:00:00+07:00
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### Connect to RDGW

The next step is to log in to the **Remote Desktop Gateway (RDGW)** server using the **Remote Desktop Protocol (RDP)**. If you are using a **Windows** computer, RDP is already available. If you are using a Mac, you need to download the RDP application [here](https://docs.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/remote-desktop-mac).

1. Login to **AWS Console** and access **EC2 Management Console**.

   ![RDGW](/images/3-RDGW/1.png?width=90pc)

2. In the **EC2** interface:

   - In the left menu, select **Instances**.
   - Check the checkbox for the RDGW server.
   - Select **Connect**.

   ![RDGW](/images/3-RDGW/2.png?width=90pc)

3. In the **Connect to Instance** interface:

   - Select **RDP Client** and select "Download Remote Desktop File".
   - Select **Get Password**.

   ![RDGW](/images/3-RDGW/3.png?width=90pc)

4. In the **Get Windows Password** interface:

   - Select **Browse** and find the key pair file you downloaded earlier.
   - Select **Decrypt Password**.

   ![RDGW](/images/3-RDGW/4.png?width=90pc)

5. When the password is decrypted, copy and save it.

   ![RDGW](/images/3-RDGW/5.png?width=90pc)

6. Open the downloaded RDP file and use the password from the previous step to log in to the RDGW server.

   - Select **Connect**.

   ![RDGW](/images/3-RDGW/6.png?featherlight=false&width=90pc)
   ![RDGW](/images/3-RDGW/7.png?featherlight=false&width=90pc)

7. Enter the password and select **OK**.

   
   ![RDGW](/images/3-RDGW/8.png?featherlight=false&width=90pc)


8. Continue by selecting **Yes**.

   ![RDGW](/images/3-RDGW/9.png?featherlight=false&width=90pc)

9. This is the screen showing successful connection to the server.

   ![RDGW](/images/3-RDGW/10.png?featherlight=false&width=90pc)

