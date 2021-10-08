Instructions for seeting up example locally using Python and Pycharm editor.

Note: You can choose to use command line or a Python editor such as Python, the steps will be very close.

1- Sign up for LaunchDarkly evaluation at: https://launchdarkly.com/start-trial/ 
2- Make sure you have python installed. At least version 3.5 or higher.
3- If you are using PyCharm, make sure it is installed. I tested on 2021.1 Community Edition.
4- Install Python launchdarkly sdk: ldclient.py (https://github.com/launchdarkly/python-server-sdk)
	If installing by command line you can use pip command from path where test application is installed
	If installing using pycharm, go to File/settings/Project/test.py
		Select Python interpreter. Click on + and type "ldclinet-py" (you should see description, version 6.9.1, author: LaunchDarkly)
		Click on "Install Package button" at bottom left.
5- Set SDK dependencies:
	In a command prompt cd to the installation directory of the sample application.
	There should already be a filled called requirements.txt (You should see the installation on the command prompt)
	type pip install -r requirements.txt

NOTE: This will only work with my evaluation settings: to change the configuration to your own setup, you will need to do the following
before running the test.py application:

1- Log into your LaunchDarkly evaluation.
2- I recommend reading the getting started documentation and videos to familiarize yourself with the platform (30 minute read)
3- In LaunchDarkly application:
	1- Create a feature flag
		You can use tutorial wizard or go to feature flags menu and click on + flag ( I used wizard because it is very useful for next step)
		Create a unique name for your feature flag in LaunchDarkly. (I used gg-main-flag)
	2- Set Up the Application (this is where you make changes the source code of the test.py application.
		For Language select "Python"
		For Select your environment, select "Production"
		Set sdk_key: replace : sdk_key = "sdk-f73ece63-300a-4e72-84a1-b2b8f88641e9" with your sdk_key in quotes" your Key is found
		in section d of the getting started wizard.
		Since you downloaded the sample application, and my file, steps a,b and c from the getting started wizard should already be completed.
		change: feature_flag_key = "gg_main_flag" - replace "gg_main_flag" with the name of the flag name you created.
		d- Initialize ld client with your specific key:
			Copy and replace the sdk key automatically generated in this section onto your test.py file.
		e- Under User: you can leave Buster Posey or change the attributes of the user. You can even use the default names from the
		   getting started wizard.
		Save changes to your test.py file

Test your application:
	Click the green run button in Pycharm from the test.py file in the editor
	From command line go to the sample application folder after you have replaced test.py with the one I created and type: >python test.py

1- In Launchadarkly quickstart wizard you should see: Great -- we received an event for your flag!
2- If you go to users, you can see that the user from your test.py code was created in LaunchDarkly under users.
3- In LD, under Feature Flags, you will see the feature flag you created (mine is gg_main_flag) you can change the flag to true and run your application
   again, you will now see that the application will display: "showing your feature:
4- You can turn of the flag again in LD, and run the application, you will now see that it now shows: "Not showing your feature"

Congratulatinons, you have successfully completed the exercise!

For the extra points, I created a flag targeting individual users.

1- I did not make any changes to the code, but created a targeting individual users in LD by doing the following:

	1- Go to Feature Flags menu
	2- click on the name of your feature flag (mine was gg_main_flag)
	3- Go to targeting section:
	4- Under targeting individual users - click on add users and select the name of your user (I used Buster Posey)
	5- Click on targeting button to turn on
	6- Click on save changes
	7- Under Insights and History, you will be able to track all the changes and tests that you ran











	
