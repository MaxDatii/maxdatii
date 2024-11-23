
# **HOW TO CREATE A UNIQUE GITHUB PAGE DESIGN**

Welcome! Follow these instructions to create your unique GitHub page design, complete with animations and custom styling.

---

## **Step 1: Set Up Your Repository**
1. Create a new repository.  
   **Note:** The repository name must exactly match your GitHub username.  
   Example: If your GitHub username is `maxdatii`, your repository name should also be `maxdatii`.
2. Check the box **“Add a README file”** during repository creation.
3. Click **“Create Repository”** to finish setting it up.

---

## **Step 2: Customize Your README**
1. Copy the code below and paste it into your `README.md` file:
   ```html
   # Hi there! 👋

   Welcome to my GitHub profile! Here's a cool animation for you:
   <img src="https://raw.githubusercontent.com/maxdatii/maxdatii/output/snake.svg" alt="Snake animation" />

   If you like this design, don't forget to ⭐ this repository and follow me for more cool stuff!
   ```
2. Replace **`maxdatii/maxdatii`** in the `<img>` URL with your own GitHub username and repository name:
   ```html
   <img src="https://raw.githubusercontent.com/YOURGITHUBNAME/YOURREPONAME/output/snake.svg" alt="Snake animation" />
   ```

3. Save the changes to your `README.md` file.

---

## **Step 3: Add the Snake Animation**
1. Open your repository and click **“Add file”** > **“Create new file”**.
2. In the “File name” field, type:
   ```
   .github/workflows/snake.yml
   ```
   **Note:** This will create both the folders and the file automatically.
3. Copy and paste the following code into the `snake.yml` file:
   ```yaml
   name: Generate snake animation

   on:
     schedule: # execute every 12 hours
       - cron: "* */12 * * *"
     workflow_dispatch:

     push:
       branches:
       - master

   jobs:
     generate:
       permissions:
         contents: write
       runs-on: ubuntu-latest
       timeout-minutes: 5

       steps:
         - name: generate snake.svg
           uses: Platane/snk/svg-only@v3
           with:
             github_user_name: ${{ github.repository_owner }}
             outputs: dist/snake.svg?palette=github-dark

         - name: push snake.svg to the output branch
           uses: crazy-max/ghaction-github-pages@v3.1.0
           with:
             target_branch: output
             build_dir: dist
           env:
             GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
   ```
4. Commit the changes to your repository.

---

## **Step 4: Run the Workflow**
1. Go to the **Actions** tab in your repository.
2. Check if the workflow has run successfully.  
   If not, click **“Generate Snake Animation”** > **Run Workflow** to start the generation manually.
3. Wait a few seconds for the workflow to complete.
4. Verify that the animation is displayed in your `README.md` file.

---

## **Final Step: Share and Show Support!**
- If you like the design, don’t forget to **star** ⭐ the repository and follow for more cool ideas.  
- You can share your unique GitHub page with others to inspire them!

---

# **PROMPT FOR ChatGPT USED TO CREATE THIS DESIGN**

You can use the following prompt to recreate or customize your GitHub profile. Replace the text with your own information to personalize your profile.

---

### **ChatGPT Prompt**:
> **Prompt:**  
> You are a highly skilled full-stack software developer, graphic designer, and GitHub guru. Please help me create a unique and minimalistic, very professional-looking `README.md` file for my GitHub profile. Below is my information. I want this page to look outstanding, so please include styles, icons, and images to impress everyone. The theme should be dark or use dark colors for the background.  
>
> **My Information:**  
> - **Name:** Max  
> - **Certifications:** AWS Certified Solutions Architect, AWS Certified Cloud Practitioner  
> - **Job Role:** DevOps Engineer and Software Developer  
> - **Skills:**  
>   - AWS, Microsoft ADO, Kubernetes, Terraform, Linux, GitOps, CI/CD Orchestration, Docker, ArgoCD, Prometheus, Splunk, Kiali, Microservices Architecture  
>   - Programming Languages: JavaScript, HTML/CSS, YAML  
> - **Languages Spoken:** English, Ukrainian, Russian, Polish  
> - **Education:** Master’s degree in Computer Science, Marketing, and Economics  
> - **Hobbies:** Tennis, running, yoga, skiing  
> - **Fun Fact:** Sci-Fi Lover: "Inspired by sci-fi movies like *Arrival*, *Interstellar*, and *Inception*, I aim to code the future—but first, I have to debug the present."

---

## **Enjoy!** 🤓  
If you liked this guide and design, don’t forget to ⭐ the repository and share it with others. Let’s make GitHub beautiful together! 🚀

