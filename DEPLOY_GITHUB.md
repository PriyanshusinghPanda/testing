# Deploying to Render via GitHub

Follow these steps to deploy your application to Render using GitHub:

## 1. Push your code to GitHub

1. Create a new repository on GitHub.

2. Initialize your local repository and push your code:
   ```bash
   cd DynamicPricingSystem
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/blinkit-app.git
   git push -u origin main
   ```

## 2. Connect to Render

1. Create a Render account at [render.com](https://render.com/) if you don't already have one.

2. In the Render dashboard, click "New" and select "Web Service".

3. Connect to your GitHub repository:
   - Choose "GitHub" as the deployment method.
   - Connect to your GitHub account if you haven't already.
   - Select the repository you created.

4. Configure the web service:
   - **Name**: Choose a name for your application (e.g., blinkit-app)
   - **Environment**: Python
   - **Region**: Choose the closest region
   - **Branch**: main
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `cd blinkitapp && gunicorn app:app`
   - **Plan**: Free (or choose a paid plan for production)

5. Add the following environment variables:
   - `SECRET_KEY`: Generate a random string or use a secure password generator
   - `PYTHON_VERSION`: 3.9.0

6. Click "Create Web Service".

Render will automatically deploy your application. Any future changes pushed to your GitHub repository will trigger automatic redeployments if you have the Auto-Deploy option enabled.

## 3. Accessing your deployed application

Once the deployment is complete, you can access your application at the URL provided by Render, which will look something like:
`https://your-app-name.onrender.com`

## 4. Troubleshooting

- If your application fails to deploy, check the logs in the Render dashboard for error messages.
- Make sure all your dependencies are correctly listed in requirements.txt.
- Verify that your application is properly configured to run on the port provided by Render via the PORT environment variable. 