# Ex.05 Design a Website for Server Side Processing
## Date:20-11-2024

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
html

<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1 align="center">Calculating Power of a Lamp</h1>
    <form action="{% url 'Result' %}" method="post">
        {% csrf_token %)
        <label for="">Intensity : </label>
        <input type="text" name="intensity-input">
        <br>
        <label for="">Resistance : </label>
        <input type="text" name="resistance-input">
        <br>
        <button type="submit">Calculate</button>
    </form>  
</body>
</html>

views.py

from django.shortcuts import render
def home(request):
    return render(request,'index.html')
def Power(request):
    if request.method == 'POST':
        intensity_value = int(request.POST.get('intensity-input'))
        resistance_value = int(request.POST.get('resistance-input'))
        power = (intensity_value**2)*(resistance_value)
        return render(request,'Result.html',{'output':power})

urls.py

from django.contrib import admin
from django.urls import path
from myapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.home,name='home'),
    path('result',views.Power,name='Result')
]

## SERVER SIDE PROCESSING:
![385227437-f240508f-f16c-4c80-857a-b156d5e3258c](https://github.com/user-attachments/assets/9fa70195-032b-4479-80b7-c62a3f35bb68)
```

## HOMEPAGE:
![385227579-e249b7d2-68fb-4e81-9a06-cc005a5a3617](https://github.com/user-attachments/assets/b0dbaa97-2f7f-445b-973b-3d3b8d749e36)
![385228923-20d763ad-db3e-4626-9ace-49544dfe88a2](https://github.com/user-attachments/assets/0361419b-afbd-4ddd-aced-0bbb20279068)

## RESULT:
The program for performing server side processing is completed successfully.
