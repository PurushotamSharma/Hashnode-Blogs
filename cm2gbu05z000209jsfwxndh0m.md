---
title: "How to Connect PostgreSQL Database to Power BI Using ODBC: A Step-by-Step Guide"
seoTitle: "How to Connect PostgreSQL Database to Power BI Using ODBC: A Step-by-S"
seoDescription: "How to Connect PostgreSQL Database to Power BI Using ODBC: A Step-by-Step Guide"
datePublished: Sat Oct 19 2024 15:41:49 GMT+0000 (Coordinated Universal Time)
cuid: cm2gbu05z000209jsfwxndh0m
slug: how-to-connect-postgresql-database-to-power-bi-using-odbc-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729352403707/212caba5-f64f-499c-bfe1-8ba5f64d5432.png
tags: writing, postgresql, data-science, data-analysis, visualization

---

#### Introduction:

Hello, data enthusiasts! 🎉 Ever found yourself wanting to seamlessly connect your PostgreSQL database to Power BI but didn’t know where to start? Well, you’re in the right place! Today, I’ll walk you through a straightforward, step-by-step process to get your PostgreSQL data flowing into Power BI using an ODBC driver. By the end of this guide, you'll be creating stunning visualizations with ease. Let’s dive in!

### Step 1: Setting Up Your PostgreSQL Database on [Neon.tech](http://Neon.tech)

[To keep](https://neon.tech/) things simple, we’ll use [Neon.tech](http://Neon.tech) to set up our [PostgreS](https://neon.tech/)QL database. If you’re new to [Neon.tech](http://Neon.tech), don’t worry! It’s super easy and user-friendly.

1. **Create a New Project:**
    
    * Head over to [Neon.tech](http://Neon.tech) and signup or log in. 🚀
        
    * Click on **"New Project"** to kick things off.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729344782821/59a5d71c-6a5f-41db-996c-14536dfb8e02.png align="left")
        
    * Write a name for your project, pick the PostgreSQL version, and [](https://neon.tech/)select your preferred cloud provider and region. For this demo, the default settings will do just fine.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729344999540/195da5e0-f16b-4a12-a6df-6d602665eaa8.png align="left")
        
    * Hit **"Create Project,"**! 🎉
        
2. **Configure Your** [**Database:**](https://neon.tech/)
    
    * Once your project is up, you[’](https://neon.tech/)ll see a dashboard. Here, you can either stick with the default branch (often named **"main"**) or create a new one if needed.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729345256404/b9a6bfaa-0ba2-495a-841b-44b89208d9d4.png align="left")
        
    * Your PostgreSQL database is now set up and ready to connect! 🙌
        
    
    ### Step 2: Installing and Configuring the ODBC Driver
    
    With the database in place, the next step is to set up an ODBC driver so that Power BI can talk to your PostgreSQL database. For this, we’ll use the **Devart PostgreSQL ODBC Driver**.
    
    1. **Download the ODBC Driver:**
        
        * Visit the Devart ODBC [Driver page.](https://www.devart.com/odbc/postgresql)
            
        * Download the version that matches your operating system (Windows, macOS, or Linux).
            
    2. **Install the Driver:**
        
        * Run the installer file you just downloaded and follow the installation steps. It’s as easy as hitting “Next” a few times! 😉
            
    3. **Configuring the ODBC Data Source:**
        
        * Open **"ODBC Data Source Administrator"** from your Start menu (make sure to choose 32-bit or 64-bit based on your OS).
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729346993480/ffa4e920-509a-4ed2-8e51-4068d5f08fbe.png align="left")
            
        * Click **"Add"** and select **Devart PostgreSQL ODBC Driver** from the list.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729347050311/8f85ef3a-c320-40d4-9a13-1ad48cecd84c.png align="left")
            
        * Then, click **"Finish."**
            
    4. **Fill in the Configuration Details:**
        
        * **Data Source Name:** Name it something meaningful (like "MyProjectDB").
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729347120836/4614a26b-c613-4cc7-9c07-6c8a30e44d2b.png align="left")
            
        * **Description:** Optional, but feel free to add one.
            
        * **Server:** Enter the IP address, domain name, or host of your database (e.g., `ep-odd-haze-a5o3gvk3.us-east-2.aws.neon.tech`).
            
        * **User ID:** Use your PostgreSQL username (e.g., `neondb_owner`).
            
        * **Password:** This is a crucial part! Unlike some setups, the ODBC driver requires the endpoint information, but there's no specific field for it. So, we include it directly in the password. Neon.tech offers several options for configuring endpoints—check out their [documentation on connection errors](https://neon.tech/docs/connect/connection-errors) for more [details.](https://neon.tech/docs/connect/connection-errors)
            
            ```plaintext
            endpoint=<endpoint_id>$<password>
            ```
            
            For instance:
            
            ```plaintext
            endpoint=ep-odd-haze-a5o3gvk3$eTQVXO7PY2Jd
            ```
            
        * **Database:** Type in your database name (e.g., `neondb`).
            
        * **SSL Mode:** Make sure SSL is enabled by going to Security Settings and selecting **"Use SSL."**
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729347913698/56bab7f4-2f80-4231-8146-e74492afb8c6.png align="left")
            
    5. **Test Your Connection:**
        
        * Hit **"Test Connection"** to see if everything’s working. If it’s a success, you’re golden! ✨ If not, double-check your details and try again.
            
    
    ### Step 3: Connecting PostgreSQL to Power BI
    
    With the ODBC driver set up, it’s time to move to Power BI. 🎨📊
    
    1. **Open Power BI Desktop:**
        
        * Launch Power BI Desktop and click on **"Get Data."**
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729348799984/a32b0030-cc9e-456e-ba7c-dd7dadcaff83.png align="left")
            
    2. **Choose ODBC Connection:**
        
        * In the “Get Data” window, type in **"ODBC"** and select it.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729348965702/46561fb8-57b9-480b-b583-01453110eb6a.png align="left")
            
        * You’ll see the DSN (Data Source Name) you created earlier. Select it and click **"OK."**
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729349022190/66475c81-2125-4123-91ff-f45b023b4b33.png align="left")
            
    3. **Enter Your Credentials:**
        
        * When prompted, enter the same username and password as before.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729349209570/09345c53-17da-495f-9d2b-b038fe18be61.png align="left")
            
        * Click **"Connect."**
            
    4. **Load Your Data:**
        
        * Select the tables you want to import from your PostgreSQL database.
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729349250522/7b516a14-7e10-4a98-bf45-e048a2ef223e.png align="left")
            
        * Click **"Load,"** and Power BI will pull in your data. 🎉
            
    5. **Create Your Visuals:**
        
        * Once the data is loaded, you’re free to create beautiful charts, graphs, and reports to bring your data to life!
            
    
    ---
    
    ### Conclusion:
    
    And there you have it! 🎉 You’ve successfully connected your PostgreSQL database to Power BI using an ODBC driver. This setup allows you to tap into your PostgreSQL data, creating stunning, data-driven insights with just a few clicks. So go ahead, explore your data, and make the most of Power BI’s powerful visualization tools!  
    
    Got stuck somewhere? Or maybe you found a cool trick while following along? Drop your comments below, and let’s chat. Happy visualizing! 📊✨
    
    Cover image credit: [EasyInsights](https://www.google.com/url?sa=i&url=https%3A%2F%2Feasyinsights.ai%2Fblog%2Fhow-to-connect-power-bi-with-postgresql%2F&psig=AOvVaw1bbW38XhrxtHieZKOj3cKJ&ust=1729438587498000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCLCU0PrimokDFQAAAAAdAAAAABAE)