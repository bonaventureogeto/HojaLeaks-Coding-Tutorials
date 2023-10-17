---
title: "How to Install and Run MongoDB"
seoTitle: "How to Install and Run MongoDB"
datePublished: Tue Oct 17 2023 08:25:05 GMT+0000 (Coordinated Universal Time)
cuid: clnu26w8v000809lc071ecfoq
slug: how-to-install-and-run-mongodb
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697530963010/d4210971-bd19-4d0b-b7e3-9d42055be200.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1697531072165/29e60ed1-8a64-4b53-8c05-1eef6385d9aa.jpeg
tags: javascript, web-development, mongodb, nodejs, databases

---

MongoDB provides different installation methods for various operating systems, so be sure to choose the one that matches your system.

**Step 1: Choose the Installation Method**

MongoDB offers various installation methods, including Community Server, Atlas (MongoDB's hosted database service), and Docker. Here, I'll cover the installation of the MongoDB Community Server, which is the open-source version of MongoDB that you can install on your local machine.

**Step 2: Download MongoDB (Community Server)**

1. Visit the MongoDB download page: [MongoDB Download Center](https://www.mongodb.com/try/download/community)
    
2. Choose your operating system (Windows, macOS, or Linux) and the package type (ZIP, MSI, or RPM).
    
    For example, if you're using Windows, you can select "Windows" and download the MSI package.
    
3. Download the package to your local machine.
    

**Step 3: Install MongoDB**

The installation steps vary depending on your operating system. Here are instructions for Windows, macOS, and Linux:

* **Windows**:
    
    1. Run the downloaded MSI installer.
        
    2. Follow the installation wizard.
        
    3. You can choose to install MongoDB as a service or use the default settings.
        
* **macOS**:
    
    1. Open the downloaded DMG file.
        
    2. Drag and drop the MongoDB icon into the Applications folder.
        
* **Linux** (using APT package manager, for example):
    
    1. Open a terminal.
        
    2. Import the MongoDB GPG key:
        
        ```bash
        wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
        ```
        
    3. Create a list file for MongoDB:
        
        ```bash
        echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
        ```
        
    4. Update the package repository:
        
        ```bash
        sudo apt-get update
        ```
        
    5. Install MongoDB:
        
        ```bash
        sudo apt-get install -y mongodb-org
        ```
        

### Errors:

```plaintext
The following packages have unmet dependencies:
 mongodb-org-mongos : Depends: libssl1.1 (>= 1.1.1) but it is not installable
 mongodb-org-server : Depends: libssl1.1 (>= 1.1.1) but it is not installable
 mongodb-org-shell : Depends: libssl1.1 (>= 1.1.1) but it is not installable
E: Unable to correct problems, you have held broken packages.
```

In case you get the error message above in Ubuntu, refer to this solution on StackOverflow [https://stackoverflow.com/questions/73656873/unable-to-install-mongodb-in-ubuntu-22-04-mongodb-org-libssl1-1](https://stackoverflow.com/questions/73656873/unable-to-install-mongodb-in-ubuntu-22-04-mongodb-org-libssl1-1)

**Step 4: Start MongoDB**

* **Windows**: If you installed MongoDB as a service, it should automatically start with your system. Otherwise, you can start MongoDB by running the `mongod` executable.
    
* **macOS** and **Linux**: Open a terminal and start the MongoDB server with the following command:
    
    ```bash
    sudo service mongod start
    ```
    

**Step 5: Verify MongoDB is Running**

You can verify that MongoDB is running correctly by opening a terminal and running the following command:

```bash
mongo
```

This will open the MongoDB shell, and you should see a prompt indicating a successful connection to the MongoDB server.

You have successfully installed and started MongoDB on your system. You can now start using MongoDB for your projects, and you can also interact with it through MongoDB drivers and tools like `mongo` Shell and MongoDB Compass.

I'd love to connect with you via [**Twitter**](https://twitter.com/bonaogeto) & [**LinkedIn**](https://www.linkedin.com/in/bonaventureogeto/)

Happy hacking!