# crop_monitoring
This systems works for keeping track the season crop dynamics based on remote sensing images.

# cropcalendar app
Please install this extension in chrome before running the system via django framework
https://chrome.google.com/webstore/detail/ignore-x-frame-headers/gleekbfjekiniecknbkamfmkohkpodhe

Guide to install cropcalendar
1.	Install anaconda 3 and setup python environment from here https://www.anaconda.com/distribution/
2.	Install google earth engine API in python https://developers.google.com/earth-engine/python_install
3.	Install Google cloud SDK https://cloud.google.com/sdk/install
4.	Create a google earth engine account from https://signup.earthengine.google.com/#!/
5.	Once you are approved for earth engine and cloud Authorize all of them by same google account
6.	Fork the project from https://github.com/ashokdahal/cropcalendar_app.git
7.	Setup on the directory in windows 
8.	Go to that folder and run python manage.py runserver from anaconda environment terminal
9.	Change the folder/file locations in /uploader/views.py as well as the user folder in gee by modifying this codes 

	filelocation=r'D:\django\cropcalendar'+ str(uploaded_file_url).replace("/",'\\')
upload_gs='gsutil -m cp '+filelocation+'  gs://shpgee/'
	upload_gee=r'earthengine upload table --asset_id=users/ashok_dahal/cropsites/'+str(filename).replace('.zip','')+' gs://shpgee/'+filename
	       
10.	Change local postgres settings in loadpostgres/views.py by modifying this codes:
D:/django/cropcalendar/download/
user="postgres",
                                        password="PASS",	
                                        host="127.0.0.1",	
                                        port="5432",	
                                        database="postgres"	
postgres://postgres:PASS@127.0.0.1:5432/postgres










Save the project and run server again. Open the browser and login to google earth engine and visit crop calendar at 127.0.0.1:8000 . Please use google chrome and have this extension installed https://chrome.google.com/webstore/detail/ignore-x-frame-headers/gleekbfjekiniecknbkamfmkohkpodhe

New links

Season 1
https://code.earthengine.google.com/73f7e4b8230bceebb9b5950fc2165139?hideCode=true

season 2
https://code.earthengine.google.com/d9c51c7e55e912c9cdc2389fb85b8f4b?hideCode=true

season 3
https://code.earthengine.google.com/7f4450126568382e964b7df7b9d1c98a?hideCode=true


