# A step-by-step of how to use the Google API "Places API"

### Before to get into code 

1. Get into the following link and create an account or sign in if you already have it.

https://cloud.google.com/maps-platform/?hl=es

2. click in the part where "console"

3. You have to create a new project. I would highly recommend you to put a credit card to get 300 dlls that you will be able 
to use during a year

4. Click on "Navigation Menu", which is the three lines at the left of the Google Cloud Logo

5. Click on API and Services, and then, on panel

6. You will see a buttom which says "enable apis and services", get into, and choose the Places API option.


7. Click on enable and now, you have your API, but you will need the KEY. Visit https://developers.google.com/maps/documentation/embed/get-api-key to know how to get your API key which will be useful to follow this
instructor


## Let's get into code

First of all, you will have to import the following libraries. 

```python
  import time
  import json
  import requests
  import pandas as pd
  import googlemaps
```
If you are using Jupyter notebooks, you will need to install googlemaps with the following command

```
pip install -U googlemaps

```

The calling of the functions is easy, but you have to understand the structure of the request and read the documentation to know
how to ask for the information that you want.

I will show you, how to make a function to make a request

```
def callingFunction():
  endpoint_url = 'https://maps.googleapis.com/maps/api/place/nearbysearch/json?'
  params = {
    'key' : key,
    'location' : location,
    'radius' : radius,
    'type' : type1
  }

  res = requests.get(endpoint_url, params= params)
  results = res.content
  return results


```
Markup : Our endoponit_url, is the variable where the link of the API will be located.
            1. Check which is the link of the information that you want
            2. You can skip this step putting the link insted of the variable in the request.get, 
            but it is good manners to located in a variable


