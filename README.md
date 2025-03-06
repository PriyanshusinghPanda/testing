# BlinkIt Application

A dynamic pricing e-commerce application with admin dashboard and price prediction.

## Deployment on Render

This application is configured for easy deployment on Render.com. Follow these steps:

### Method 1: Using the Deploy Button

1. Click the deploy button below:
   
   [![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

2. This will use the `render.yaml` configuration file to set up your application automatically.

### Method 2: Manual Deployment

1. Create a new account or log in to [Render](https://render.com/).

2. From the dashboard, click "New" and select "Web Service".

3. Connect your GitHub repository or use the public repository URL.

4. Configure your web service with the following settings:
   - **Name**: Choose a name for your application (e.g., blinkit-app)
   - **Environment**: Python
   - **Region**: Choose the region closest to your users
   - **Branch**: main (or your preferred branch)
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `cd blinkitapp && gunicorn app:app`
   - **Plan**: Select the appropriate plan (Free tier works for testing)

5. Add the following environment variables:
   - `SECRET_KEY`: Generate a random secret key
   - `PYTHON_VERSION`: 3.9.0

6. Click "Create Web Service" to deploy your application.

## Local Development

To run this application locally:

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/blinkit-app.git
   cd blinkit-app
   ```

2. Create and activate a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Run the application:
   ```
   cd blinkitapp
   python app.py
   ```

5. Open http://localhost:5000 in your browser.

## Features

- Dynamic pricing based on location
- Price prediction algorithm
- Multiple order types (Normal, Quick, Scheduled)
- Admin dashboard for product and inventory management
- User authentication and profiles
- Shopping cart functionality