# noby Premium Toy Store & Collector Showcase

An executive, high-end toy store and diecast collector showroom web application built with **React**, **Vite**, **TypeScript**, and **Tailwind CSS**. It is fully responsive, optimized for desktop and mobile, and supports custom local cart workflows in Indian Currency (₹).

---

## 🎯 Why does opening `index.html` directly show a blank page?

When you double-click `index.html` directly from your file manager (which opens with the `file://` protocol), the browser displays a blank page. This is **expected modern web behavior** due to:

1. **CORS Security Restrictions**: Modern browsers block JavaScript ES Modules (`<script type="module">`) loaded via the `file://` protocol. 
2. **On-the-Fly Compilation**: React & TypeScript files (`.tsx`) require a development build server to compile and run in the browser.

To run and view the app locally on your computer, you need to spin up a quick local web server as explained below.

---

## 🚀 How to Run the App Locally (Step-by-Step)

### Prerequisites
Make sure you have **Node.js** (v18 or higher) installed on your computer. You can download it from [nodejs.org](https://nodejs.org/).

### Steps

1. **Unzip the Downloaded Folder**
   Extract the downloaded ZIP file to a folder of your choice.

2. **Open Terminal / Command Prompt**
   Open your terminal (macOS/Linux) or Command Prompt/PowerShell (Windows) and navigate into the extracted folder:
   ```bash
   cd /path/to/extracted/folder
   ```

3. **Install Dependencies**
   Run the following command to download and install all the required web libraries:
   ```bash
   npm install
   ```

4. **Start the Development Server**
   Spin up the local development server by running:
   ```bash
   npm run dev
   ```

5. **Open the Web Application**
   The terminal will display a local address (usually `http://localhost:3000` or `http://localhost:5173`). Click or copy-paste that link into your web browser to run and explore the application!

---

## 📦 Creating a Production Build

To build the static files for production deployment (e.g., to host on Vercel, Netlify, GitHub Pages, or a custom server):

1. **Build the assets**:
   ```bash
   npm run build
   ```
   This generates a `dist/` directory containing the compiled, highly optimized HTML, CSS, and JS files.

2. **Locally preview the production build**:
   ```bash
   npm run preview
   ```
   This serves the static build locally so you can verify everything is pristine before deploying.

---

## 🌐 Deploying to GitHub Pages

We have pre-configured this project to build perfectly on GitHub Pages! The `vite.config.ts` uses relative paths (`base: './'`), meaning it will work flawlessly regardless of your GitHub repository name.

Here are the two ways you can publish this site to GitHub Pages:

### Method A: Automated Deployment via GitHub Actions (Recommended)

We created an automated pipeline in `.github/workflows/deploy.yml`. When you push your code to GitHub, GitHub will automatically compile and deploy your store!

1. Create a new repository on GitHub and push this project's code to the `main` or `master` branch.
2. In your GitHub Repository, go to **Settings** -> **Pages** (in the left-hand sidebar).
3. Under **Build and deployment**:
   - For **Source**, select **GitHub Actions** from the dropdown.
4. Go to the **Actions** tab at the top of your repository to see your site building and deploying automatically! Once completed, GitHub will provide your live URL (e.g., `https://<username>.github.io/<repo-name>`).

### Method B: Manual Deployment via `gh-pages` package

If you prefer to deploy directly from your local terminal using an npm script:

1. Install the deployment helper package:
   ```bash
   npm install --save-dev gh-pages
   ```
2. Open your `package.json` file and add the following two scripts under the `"scripts"` block:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   ```
3. Initialize a git repository and add your GitHub remote URL if you haven't already:
   ```bash
   git init
   git remote add origin https://github.com/USERNAME/REPO_NAME.git
   ```
4. Run the deploy script to publish your app:
   ```bash
   npm run deploy
   ```
   This will build the app and push the compiled static files to a secure `gh-pages` branch on your GitHub repository automatically!

---

## ✨ Features & Technology Stack
- **Modern UI Canvas**: Styled with a dark-slate design, luxurious accents (`#cca43b` gold-bronze), and generous negative space.
- **Responsive Layout**: Dynamic layout adaptation for all screens, featuring a dedicated sticky bottom mobile navigation bar.
- **Advanced Filtering**: Live, fluid filtering by scale (1:64, 1:18, etc.), release series, and release year, complete with active filter tags.
- **Valuables Cart**: Persistent Indian Rupees (₹) pricing, custom shipping threshold bars, and simulated checkout.
