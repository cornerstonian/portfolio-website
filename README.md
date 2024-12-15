<h1>Deploy a Website Using Azure and GitHub (Automation, CI/CD)</h1>

VISIT SITE: https://kind-island-058855e1e.4.azurestaticapps.net/  

Deploying a static responsive website in Azure using GitHub involves integrating **Azure Static Web Apps** with a GitHub repository. This method automates deployments and is ideal for collaborative and CI/CD workflows.

**What is CI/CD (Continuous Integration and Continuous Deployment)?** is a practice in software development that automates the process of integrating code changes and deploying them to production. 

- **Continuous Integration (CI)** involves automatically testing and integrating code changes into a shared repository multiple times a day or as often as needed.
- **Continuous Deployment (CD)** ensures that these changes are automatically deployed to production environments after passing tests, which gives us rapid and reliable delivery of software.

<img width="1088" alt="image" src="https://github.com/user-attachments/assets/ba07a20c-3434-4a86-994f-ff59bb0b5a25" />

  
---

### Environments and Technologies Used ###

  - Visual Studio Code (VS Code)
  - HTML
  - CSS
  - JavaScript
  - Microsoft Azure (Virtual Machines/Compute)
  - Git
  - Command Line

### Benefits of Using GitHub with Azure Static Web Apps ### 

- **CI/CD Integration**: Automatic deployments via GitHub Actions.
- **Global CDN**: Fast performance with built-in Azure CDN.
- **Custom Domains and HTTPS**: Easy setup for secure custom domains.
- **Free Hosting Tier**: No cost for basic static web apps
---

### **Steps to Deploy a Static Website Using Azure and GitHub**

### **1. Prepare Your Static Website and GitHub Repository**

1. **Prepare the Website Files**
    - Create a responsive website with HTML, CSS, and JavaScript.
    - Ensure all files are in a single directory (e.g., `index.html`, `style.css`, `scripts.js`).
2. **Test Locally**
    - Verify that the website works correctly on your local machine.
3. **Push to GitHub**
    - Create a repository on GitHub for your project.
    - Clone the repository to your local machine:
        
        ```bash
        git clone https://github.com/cornerstonian/portfolio-website.git
        cd portfolio-website
        
        ```
        
    - Add your website files to the repository:
        
        ```bash
        git status
        git add .
        git commit -m "Initial commit"
        git push origin main
        
        ```
        
      <img width="645" alt="Screen Shot 2024-12-15 at 9 47 14 AM" src="https://github.com/user-attachments/assets/6339a332-5de7-4df7-9217-8c704e628f9f" />

---

### **2. Set Up Azure Static Web Apps**

1. **Sign in to Azure Portal**
    - Visit [Azure Portal](https://portal.azure.com/).
2. **Create a New Static Web App**
    - In the search bar, type **Static Web Apps** and select **Static Web Apps** from the results.
    - Click **+ Create**.

<img width="1439" alt="Screen Shot 2024-12-15 at 9 55 20 AM" src="https://github.com/user-attachments/assets/6869cb50-c6b1-42ca-936e-bef9a788230f" />  


    
          
4. **Configure the Static Web App**
    - **Subscription**: Choose your Azure subscription.
    - **Resource Group**: Create a new one or select an existing one.
    - **Name**: Provide a unique name for your app.
  
      <br>

    <img width="1430" alt="Screen Shot 2024-12-15 at 9 55 42 AM" src="https://github.com/user-attachments/assets/5e7c3044-5f16-4bef-a424-6a5935a09452" />  

    <br>
    <br>

    - **Region**: Select a region close to your audience.
    - **Deployment Source**: Select **GitHub**.
    - **GitHub Sign-In**: Authenticate with GitHub if prompted.
    - **Organization**: Select your GitHub username or organization.
    - **Repository**: Choose the repository with your static website.
    - **Branch**: Select the branch (e.g., `main`) that contains the website files.
    - **Build Details**:
        - **App Location**: `/` (root folder if your files are in the repository root).
        - **Output Location**: Leave blank for basic HTML/CSS/JS websites.
4. **Review and Create**
    - Verify the configuration and click **Create**.
  
      <img width="1400" alt="Screen Shot 2024-12-15 at 10 01 05 AM" src="https://github.com/user-attachments/assets/ae18c0ad-f6d9-4340-9719-e8a2cf70282d" />

      <br>

      <img width="1405" alt="Screen Shot 2024-12-15 at 10 01 36 AM" src="https://github.com/user-attachments/assets/3f34c1e3-e176-4613-8235-6671c5f0d46e" />



---

### **3. Automated Deployment via GitHub Actions**

1. **GitHub Actions Workflow**
    - Azure Static Web Apps automatically generates a GitHub Actions workflow in your repository.
    - You can view it under https://github.com/cornerstonian/portfolio-website/blob/main/.github/workflows/azure-static-web-apps-kind-island-058855e1e.yml .
  
      <br>  

      ![telegram-cloud-photo-size-1-5114007896127024770-y](https://github.com/user-attachments/assets/f1b8aa0c-d3ea-4d92-8b2e-7f6c4fe5df82)


    
1. **Trigger the Deployment**
    - Push any changes to the `main` branch to trigger the GitHub Actions workflow:
        
        ```bash
        git add .
        git commit -m "Update website content"
        git push origin main
        
        ```
        
    - The workflow builds and deploys your website automatically.
2. **Monitor Deployment**
    - Go to the **Actions** tab in your GitHub repository to monitor the progress of the deployment.

---

### **4. Test Your Static Web App**

1. **Access Your Website**
    - After deployment, Azure provides a default URL for your website, e.g., https://kind-island-058855e1e.4.azurestaticapps.net/ .
    - Test the website and ensure it is responsive.

---

### **5. (Optional) Configure a Custom Domain**

1. **Purchase a Domain**
    - Use Azure Domains or a third-party registrar.
2. **Map the Domain**
    - In the Azure Portal, go to your Static Web App → **Custom Domains**.
    - Add your custom domain and verify ownership by configuring a CNAME or TXT record in your domain registrar.
3. **Enable HTTPS**
    - Azure automatically provisions an SSL certificate for your custom domain.

---

### **6. Update Your Website**

1. **Make Changes Locally**
    - Edit your website files and fix the issues locally, push your changes to GitHub, repeat the process.
2. **Push Updates to GitHub**
    - Push changes to the `main` branch, and Azure will automatically deploy the updated version.
    -  Use: `git add` ., `git status`, `git commit`, and `git push`.
  
      <br>
  
      <img width="1412" alt="Screen Shot 2024-12-15 at 10 14 40 AM" src="https://github.com/user-attachments/assets/9a28a9d2-f04b-4c51-b8b5-5ea7c5857dce" />


---

### **7. Monitor and Manage**

1. **Monitor Usage**
    - Use the **Monitoring** section in Azure Portal to track usage, errors, and traffic.
2. **Manage Settings**
    - Adjust configurations, such as custom headers or access restrictions, in the Static Web App settings.
