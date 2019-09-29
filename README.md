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
