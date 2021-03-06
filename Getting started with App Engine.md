# Lab: Google Cloud Fundamentals: Getting Started with App Engine
The objectives in this lab are:
  - Initialize App Engine.
  - Preview an App Engine application running locally in Cloud Shell.
  - Deploy an App Engine application, so that others can reach it.
  - Disable an App Engine application, when you no longer want it to be visible.

#Steps
1. Initialize App Engine
    - Initialize your App Engine app with your project and choose its region. This allows you to select the region where you want your application to be located.
         - gcloud app create --project=[YOUR_PROJECT_NAME]

    - Clone the source code repository for a sample application in the hello_world directory: 
         - git clone https://github.com/GoogleCloudPlatform/python-docs-samples

    - Navigate to the source directory:
         - cd python-docs-samples/appengine/standard_python3/hello_world

2. Run Hello World application locally. You run the Hello World application in a local, virtual environment 
    - Download and update the packages list 
          - sudo apt-get update

    - Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system
         - sudo apt-get install virtualenv
         - virtualenv -p python3 venv

    - Activate the virtual environment.
         - source venv/bin/activate

    - Navigate to your project directory and install dependencies
         - pip install -r requirements.txt

    - Run the main application
         - python main.py

    - In Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application.

    - To end the test, press Ctrl+C to abort the deployed service

3.  Deploy and run Hello World on App Engine. Deploy your application to the App Engine Standard environment
      - Navigate to the source directory:
         - cd ~/python-docs-samples/appengine/standard_python3/hello_world

      - Deploy your Hello World application.
         - gcloud app deploy
         
      - Launch your browser to view the app at http://YOUR_PROJECT_NAME.appspot.com
         - gcloud app browse
    Copy and paste the URL into a new browser window

4. Disable the application. 
           - gloud app stop
