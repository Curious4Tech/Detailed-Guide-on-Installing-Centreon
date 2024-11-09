# Detailed-Guide-on-Installing-Centreon
This guide walks you through the complete installation and configuration process of Centreon, a powerful IT monitoring tool.

# Web and Post Installation of Centreon

Once Centreon is installed on your server, access its web interface to complete the setup. Follow these steps for a successful configuration:


# Centreon Installation Guide

This guide provides a step-by-step walkthrough for installing and configuring Centreon, a comprehensive IT monitoring tool.

## Prerequisites

Ensure that Centreon is installed on your server before starting the web installation process. Access Centreon’s web interface to complete the setup.

## Web Installation

### 1. Access the Centreon Web Interface
-Open your command prompt or terminal in your centreon server and then enter the following command:
```bash
ip a
```

![image](https://github.com/user-attachments/assets/ce0704c2-0215-4d43-b62c-852206df661b)

This will help you find the IP of centreon server

- Open a browser and go to:
  ```
  http://<IP>/centreon
  ```
- Replace `<IP>` with the server’s IP address.

  
![image](https://github.com/user-attachments/assets/bf1b644e-e15f-4d7e-9a3a-6b5084e2c9c0)


### 2. Step 1: Welcome to Centreon Setup
- The Centreon setup wizard will appear. Click **Next** to start.

![image](https://github.com/user-attachments/assets/26d0b1c2-bf9b-45c6-b82f-51edb5d43497)


### 3. Step 2: Dependency Check
- Centreon will check for required modules and prerequisites.
- If needed, apply corrective actions and click **Refresh**.
- Once all checks pass, click **Next**.

![image](https://github.com/user-attachments/assets/649c0c7a-b546-4ee3-ab9a-a80a6cc10eb1)


### 4. Step 3: Monitoring Engine Information
- Define paths for the monitoring engine. Use the default paths.
- Click **Next** to proceed.

![image](https://github.com/user-attachments/assets/7c268ce1-0905-4e83-aa81-311415febf42)


### 5. Step 4: Broker Module Information
- Define paths for the broker module. Using the defaults is recommended.
- Click **Next**.

![image](https://github.com/user-attachments/assets/3ac10463-420e-46cd-a094-8dfba089968b)


### 6. Step 5: Admin Account Setup
- Set up the admin account:
  - Enter the **username** and **password** (must be at least 12 characters with uppercase, lowercase, numbers, and special characters).
- Click **Next**.
  

![image](https://github.com/user-attachments/assets/8bb1ebf3-20eb-459a-ae38-c7bb1085aaff)



### 7. Step 6: Database Information
- Enter database details:
  - **Database Host Address**: For a local database, leave blank (default is `localhost`). For a remote database, enter its IP.
  - **Root User/Password**: Provide root credentials or a custom user with root privileges.
  - **Database User/Password**: Enter credentials for the Centreon database user.
- Click **Next**.

![image](https://github.com/user-attachments/assets/3f991ad4-18b1-4b52-9a67-79cbaed717cf)


### 8. Step 7: Installation Process
- The wizard will create a configuration file and the database structure.
- Once complete, click **Next**.

![image](https://github.com/user-attachments/assets/e3747d35-05dd-4f61-9ee9-f14829f73721)


### 9. Step 8: Module Installation
- Choose the modules and widgets to install, then click **Install**.
- When finished, click **Next**.

![image](https://github.com/user-attachments/assets/2f080fc9-84de-4a37-aa4b-6203fd65f527)


### 10. Step 9: Installation Complete
- A summary screen will appear with the latest Centreon updates.
- Click **Finish** to end the setup. You can now log in with the admin account and begin monitoring.


![image](https://github.com/user-attachments/assets/cfff2782-e959-4f93-b0b8-2b05d06a9bfe)

---

## Initialization of Monitoring

After installation, configure pollers and start monitoring services.

### 1. Configure Pollers
- In the Centreon interface, go to **Configuration > Pollers**.
  

![image](https://github.com/user-attachments/assets/fd9addfa-7bc5-4359-95c5-a5924b60ab53)


- Select **Central** and click **Export Configuration**.
  

  ![image](https://github.com/user-attachments/assets/9ce93b7f-4f77-4d95-9797-37bea91c03e8)


- Check **Move Export Files** and click **Export**.
  

![image](https://github.com/user-attachments/assets/be0ddfbc-0f82-44e4-8a8b-179e0fcdaffa)

- After clicking on **Export**, if everything is **ok**, you should see **ok** for every operation.


![image](https://github.com/user-attachments/assets/f5fdd8fc-a5e4-47ff-bfb9-529ef2f5ea5e)


### 2. Start Monitoring Services
- Log into the server terminal and run the following commands:
  ```bash
  systemctl restart cbd centengine
  systemctl restart gorgoned
  ```

![image](https://github.com/user-attachments/assets/2155a86d-2fe6-463c-95b4-0bffb1c19523)


### 3. Enable Passive Monitoring Services
- Start SNMP traps and Centreon Trap Daemon:
  ```bash
  systemctl start snmptrapd centreontrapd
  ```
- To monitor this server, start the SNMP daemon:
  ```bash
  systemctl start snmpd
  ```
  
![image](https://github.com/user-attachments/assets/d0704246-c34e-44e0-aa5f-de422b2cc2e4)




- Everything is good to go now 


![image](https://github.com/user-attachments/assets/ab28761f-f3c7-4873-b72b-936e103cd6db)


---

## Installing Extensions

1. Go to **Administration > Extensions > Manager** in the Centreon interface.
2. Click **Install all** to automatically install available extensions.


![image](https://github.com/user-attachments/assets/574f8225-5ce9-4115-85a1-b41241da8aec)

---

## Security Recommendations

To secure your Centreon platform:
- Enforce strong password policies.
- Limit access based on user roles.
- Regularly update Centreon for security patches.

---

Your Centreon setup is now complete! You’re ready to start monitoring your IT infrastructure.

---

## Troubleshooting & Support

If you encounter any issues during the setup, refer to the [official Centreon documentation](https://docs.centreon.com/) or seek help from the community.
