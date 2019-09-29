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

The calling of the functions is easy, but you have to understand the structure of the request and read the documentation to know
how to ask for the information that you want.

I will show you, how to make a function to make a request

```python
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
  results = json.loads(results)
  return results


```
Our endoponit_url, is the variable where the link of the API will be located:

            1. Check which is the link of the information that you want.
            
            2. You can skip this step putting the link insted of the variable in the request.get, 
            but it is good manners to located in a variable
            
You have to define your params. This will change according to the link that you are using. That is why is important to read the 
documentation, because there are the parameters that every link uses.

```python
  endpoint_url = 'https://maps.googleapis.com/maps/api/place/nearbysearch/json?'
  params = {
    'key' : key,
    'location' : location,
    'radius' : radius,
    'type' : type1
  }

```
Finally, we use the request, to put or parameters into the link to get the API, it will return us a json and we load it with the 
function json.loads()

```python


  res = requests.get(endpoint_url, params= params)
  results = res.content
  results = json.loads(results)
  return results


```
We have done the request, but, let's give it some meaning to that information

### Now, I will show you how to put that information into a pandas

To put that information in a DataFrame, it is really easy and you will need only one line.

```python

  dataFrame = pd.read_json(json.dumps(upy['results']), orient='records')

```
Pandas has a function to convert a json into a DataFrame. Remember that we are working with a dictionary, so check before where
are the results in that dictionary, because, as you can see in the line above, we had to specify the ubication in the dictionary.

##### Have you seen it? It is really easy, but remember! not all the API use the same link or the same parameters. The difficult
##### part is read the documentation, so, read it, and use the basis according to that information.


### Wait! We haven't finished. All you have learned, have a other way to do it and it is with the library googlemaps.

If you are using Jupyter notebooks, you will need to install googlemaps with the following command

```
pip install -U googlemaps

```

If you skip this part, you won't be able to use this library, so do it and check the next step.

Once you have that library, you have to make a variable in order to locate your API key.

```python
  
  gmaps = googlemaps.Client(key = 'Your API KEY')

```

Now, you can use all the function of the library. e.g:

```
  places = gmaps.places_nearby(location = '20.988459, -89.736768', radius = 2000, type = 'all', open_now = False)
  UPY = pd.read_json(json.dumps(places['results']), orient = 'columns')

```
What do you think this function does? Exactly! the same as the function above, but now, you did not have to make a function.

But, maybe you are saying, this is too easy, why you did a function above? 

Remember that the easy part is the call of the function, but you have to read the documentation which is the difficult part.
Every API have a diferent link, diferent parameters, so, check it, and get all the information that you want











