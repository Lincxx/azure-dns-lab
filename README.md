# Azure DNS Lab
---
In this lab we are setting up DNS on DC-1 
---

### A-Record Exercise
### Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
### Connect/log into Client-1 as an admin (mydomain\jane_admin)
### From Client-1 try to ping “mainframe” notice that it fails
![step1](https://github.com/user-attachments/assets/553573d9-7a69-4807-8bfb-80e81d52924d)
![step2](https://github.com/user-attachments/assets/16e44437-75ef-4dd2-ae11-abdf70eabd85)

### Nslookup “mainframe” notice that it fails (no DNS record)
![step3](https://github.com/user-attachments/assets/39db4c07-add7-41a7-b975-b1ad6b8e9c0e)
![step4](https://github.com/user-attachments/assets/1c02af5c-9ac4-47f0-a2b1-5bf9eee44910)
![step5](https://github.com/user-attachments/assets/c6e14cde-3a4a-4b1f-955e-ada40fafc293)

### Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address
![step12](https://github.com/user-attachments/assets/5e1f19a5-a498-4add-a5ef-65581debf884)
![step13](https://github.com/user-attachments/assets/3ee42f2f-d63c-4123-abd2-7ee11de05e27)
![step14](https://github.com/user-attachments/assets/6b5ed193-f303-465b-8c32-713d205c1b55)
![step15](https://github.com/user-attachments/assets/6de0b206-e347-4a3a-b278-ffff8ee8a9ae)
![STEP16](https://github.com/user-attachments/assets/8eb3fa40-913e-40e7-829a-69246a0d0ffd)

### Go back to Client-1 and try to ping it. Observe that it works
![step17](https://github.com/user-attachments/assets/e85f36e3-f306-41f9-a8db-6ef54cd6ad98)
![step18](https://github.com/user-attachments/assets/3dbf903d-64d1-43e4-bb56-e4bdf6f79a6a)

### Local DNS Cache Exercise
### Go back to DC-1 and change mainframe’s record address to 8.8.8.8
![step19](https://github.com/user-attachments/assets/e57c4459-6c4a-4c50-8770-b1509352eb2d)
![step20](https://github.com/user-attachments/assets/bf8df2d7-9197-4e54-bffa-eb30ad525df1)

### Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
![step21](https://github.com/user-attachments/assets/e67211d1-cd8b-4bde-a4e2-5734acf11249)

### Observe the local dns cache (ipconfig /displaydns)
![step22](https://github.com/user-attachments/assets/58fda0a6-d847-4406-b232-57bda35a6ebf)
![step23](https://github.com/user-attachments/assets/1f4b0bd0-f8e1-4501-95e7-d6d3b94ddaac)

### Flush the DNS cache (ipconfig /flushdns).
![step24](https://github.com/user-attachments/assets/084a7e2d-acec-4cf2-b886-4a8f6281d38a)

### Observe that the cache is empty (ipconfig /displaydns)
![step25](https://github.com/user-attachments/assets/2b141b44-182e-4c44-8b4a-4480538d7fc5)

### Attempt to ping “mainframe” again. Observe the address of the new record is showing up

### CNAME Record Exercise
### Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”
![step26](https://github.com/user-attachments/assets/9553a80e-7821-4f85-b5c0-18c122ca60b0)
![step27](https://github.com/user-attachments/assets/cdd16812-517f-4f33-b9f7-31b38d44707c)

### Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record
![step28](https://github.com/user-attachments/assets/7c35cbd5-641f-40f7-9273-4051add28c81)

### On Client-1, nslookup “search”, observe the results of the CNAME record
![step29](https://github.com/user-attachments/assets/ee124324-fbb6-4128-914c-ecca2756fa30)
