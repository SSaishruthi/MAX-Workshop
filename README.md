# Workshop Links

## Model Asset Exchange Project page: 

https://developer.ibm.com/exchanges/models/

## Sample Jupyter notebook explaining how to access the models: 

https://github.com/CODAIT/MAX-SVL-Workshop/blob/master/Exploring_MAX/Exploring%20MAX.ipynb

## Long-running instances and sample app: 

[Long running instances links](long_running_instances.md)

# TO DO

## Try REST API

1. Choose model of your choice and click on `Try the API`
2. Swagger UI for the REST API will open, you can see three endpoints:
    
    * /model/labels
    * /model/metadata
    * /model/predict
    
3. Click on `/model/predict` and then click `Try it out`. 
4. Provide input of your choice and click on `Execute` to run the model.

## Try accessing using ipython notebook

1. Open google colab. 
2. Upload test images into colab using `Table of contents` -> `File` -> `Upload File`.

Below is the sample for object detector. Use `Image Caption Generator model` instead of Object detector model and observe the output.

```
image_path = 'od.jpg'
url = 'http://max-object-detector.max.us-south.containers.appdomain.cloud/model/predict'
files = {'image': ('image.jpg', open(image_path, 'rb'), 'images/jpeg') }
response = requests.post(url, files=files).json()
print(response)
```


Solution: https://github.com/CODAIT/MAX-SVL-Workshop/blob/master/Exploring_MAX/Exploring%20MAX.ipynb

Demo notebook for object detector to draw bounding box: https://github.com/IBM/MAX-Object-Detector/blob/master/demo.ipynb


## Create you own web app

1. Clone the repository.

App: https://github.com/IBM/max-tutorial-app-python

```
git clone https://github.com/IBM/max-tutorial-app-python.git
```

Install dependencies
```
pip install -r requirements.txt
```

2. Open app.py in a suitable editor and complete `TODO T1` and `TODO T2`.

3. Run `python app.py --ml-endpoint http://max-object-detector.max.us-south.containers.appdomain.cloud`

Solution:

TODO T1
https://github.com/IBM/max-tutorial-app-python/blob/14136e8b4da32f5541d8bb0370c3082e8da512a3/app.py#L118
Fill **TODO T1** with model URL which is ‘/model/predict’

TODO T2
https://github.com/IBM/max-tutorial-app-python/blob/14136e8b4da32f5541d8bb0370c3082e8da512a3/app.py#L145
Model API returns predictions in JSON format. To retrieve result, replace **TODO T2** With JSON key ‘Predictions’. 


