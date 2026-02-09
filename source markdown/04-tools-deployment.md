---
title: "tools deployment"
author: "Martina"
date: 2026-02-09
---

# GitHub Pages
Last Updated : 20 Jan, 2026
GitHub Pages lets you host static websites directly from a GitHub repository for free, making it easy to share personal or project sites.

Free Hosting: GitHub Pages is free to use for both personal and project sites.
Ease of Setup: No complex configurations are needed; simply push your site to a GitHub repository.
Version Control: Since it’s tied to Git, you have full control over versioning and collaborative edits.
Custom Domain Support: GitHub Pages allows you to connect your own custom domain easily.
Built-in HTTPS: Securing your site with HTTPS is simple and free.
Types of GitHub Pages Sites
GitHub Pages allows you to host websites either for your GitHub account/organization or for individual repositories.

## User/Organization Sites
These sites are tied to your GitHub username or organization name and are hosted at username.github.io.
Project Sites: These sites are tied to a specific repository and are hosted at username.github.io/repository.
Deployment Methods to GitHub Pages
There are various ways to deploy a project to GitHub Pages, depending on your project's nature and your preference for handling it post-deployment.

**Basic Code for deployment**


// src/App.js
import './App.css';

function App() {
    return (
        <div className="App">
            <h1>Welcome to github pages</h1>
            <h3>this was published using github pages</h3>
        </div>
    );
}

export default App;
1. Deploying a Static Site from the main or master Branch
This is the simplest approach, where your static site is hosted directly from the root of your main or master branch.

Step 1: Navigate to the repository settings

*In the "GitHub Pages" section, select the main or master branch as the source and save changes.*

cd my-project
Step 2: Initialize Git repository and commit files

git init
git add .
git commit -m "Initial commit"
Step 3: Create a new repository on GitHub and push your code

git remote add origin https://github.com/username/my-project
git push -u origin main
Enable GitHub Pages in the repository settings.

GitHub-Pages
GitHub Pages Settings
Output

After completing the above steps, your site will be live at https://username.github.io/my-project/

## OutPut
Deploying a Static Site from the main or master Branch
2. Deploying from a gh-pages Branch
This method involves using a dedicated gh-pages branch for GitHub Pages, allowing you to keep your main development branch separate from the deployment branch.

1. Create and switch to the gh-pages branch git checkout --orphan gh-pages
2. Add your static files git add .
git commit -m "Deploy site to GitHub Pages"
3. Push the branch to GitHub

git push origin gh-pages
Output

Your site will be live at https://username.github.io/my-project/

OutPut
Deploying from a gh-pages Branch
3. Deploying with GitHub Actions
GitHub Actions can automate the deployment process, especially useful for projects that require a build step (like React or Next.js).

1. Create a .github/workflows directory mkdir -p .github/workflows
2. Create a deploy.yml file in the .github/workflows folder touch .github/workflows/deploy.yml
3. Add the following workflow configuration


# .github/workflows/deploy.yml

> name: Deploy to GitHub Pages

on:
    push:
        branches:
            - main

jobs:
    build:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v2
            - name: Set up Node.js
              uses: actions/setup-node@v2
              with:
                  node-version: "18"
            - run: npm install
            - run: npm run build
            - name: Deploy to GitHub Pages
              uses: peaceiris/actions-gh-pages@v3
              with:
                  github_token: ${{ secrets.GITHUB_TOKEN }}
                  publish_dir: ./build
Step 4: Commit the Workflow File

git add .github/workflows/deploy.yml
git commit -m "Add GitHub Actions workflow for deployment"
git push origin main
After you push the deploy.yml file to the main branch, GitHub Actions will automatically run the workflow. You can monitor its progress in the Actions tab of your GitHub repository.

Your site will be live at https://your-username.github.io/my-app.

Output

### OutPut
4. Deploying a React or Next.js Project
Step 1: For this method you have to update your package.json file

{
    "name": "my-app",
    "version": "0.1.0",
    "private": true,
    "homepage": "https://your-username.github.io/my-app",
    "dependencies": {
        "react": "^17.0.2",
        "react-dom": "^17.0.2",
        "react-scripts": "4.0.3"
    },
    "scripts": {
        "start": "react-scripts start",
        "build": "react-scripts build",
        "test": "react-scripts test",
        "eject": "react-scripts eject"
    }
}
Step 2: Build the project

npm run build
Step 3: Install gh-pages and deploy

npm install gh-pages --save-dev
npx gh-pages -d build
Output
Your React or Next.js site will be live at https://username.github.io/my-project/

OutPut
Deploying a React or Next.js Project
Advantages of Using GitHub Pages
Pros

#### Cons

- Free hosting
- Limited to static content
- Easy integration with GitHub
- No server-side processing
- Custom domains available
- Private repositories supported (with limitations)
- Supports Jekyll for static site generation
- Not suitable for large-scale apps
- Version control built-in
- Limited customization options

Best Practices for Securing Content on GitHub Pages
Here are some best practices:

Use strong passwords and enable two-factor authentication (2FA) to secure your account.
Keep the repository private when working with sensitive content.
Limit collaborator access to only trusted contributors.
Apply a Content Security Policy (CSP) to prevent XSS attacks.
Regularly update dependencies to reduce security vulnerabilities

# code blokovi



{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "launch",
      "name": "Pokreni Node aplikaciju",
      "program": "${workspaceFolder}/index.js",
      "skipFiles": ["<node_internals>/**"]
    }
  ]
}

{
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "editor.formatOnSave": true,
  "files.autoSave": "afterDelay",
  "workbench.colorTheme": "Default Dark+"
}

# slike
![slika br.2](![<../assets images/pexels-pixabay-270348.jpg>)](<../assets images/pexels-punttim-52608.jpg>))
[link za sliku br.2](https://images.pexels.com/photos/52608/pexels-photo-52608.jpeg)

## tablica
| Tehnologija | Vrsta | Opis |
|------------|------|------|
| HTML | Markup jezik | Struktura web stranice |
| CSS | Stilovi | Izgled i raspored elemenata |
| JavaScript | Programski jezik | Interaktivnost |
| PHP | Backend jezik | Obrada podataka |

### link na izvore
- https://en.wikipedia.org/wiki/Web_development