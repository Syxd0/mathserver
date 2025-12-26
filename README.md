# Ex.05 Design a Website for Server Side Processing
# Date:
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
home.html
<html>
  <head>
   <title>Lamp Power Calculator</title>
   <style>
       body {
           background: black; 
           
       }

    h1 {
        color: white;
        font-size: 28px;
    }

    .container {
        background-color: #ffffff;  
        width: 500px;
        padding: 50px; 
    }

    label {
        font-size: 26px;
        color: #333333;
    }

    input {
        width: 80%;
        font-size: 24px;
        border-radius: 8px;
        border: 2px solid #080707;
    }

    button {
        font-size: 24px;
        background-color: black;
        color: white;
        border-radius: 5px;
    }

    button:hover {
        background-color: black;
    }

    h2 {
        color: black;
        font-size: 24px;
    }
</style>

 </head>
 <body>
  <center>
  <h1>Incandescent Bulb Power Calculator</h1>

<div class="container">
    <form method="POST">
        {% csrf_token %}
        <label>Intensity (I):</label>
        <input type="number" name="intensity" required>

        <label>Resistance (R):</label>
        <input type="number" name="resistance" required>

        <button type="submit">Calculate Power</button>
    </form>

    {% if result %}
        <h2>Power (P) = {{ result }} Watts</h2>
    {% endif %}
</div>
</center>
</body>
</html>

views.py

from django.shortcuts import render

# Create your views here.
def home(request):
    result = "________"

    if request.method == "POST":
        I = request.POST.get("intensity")
        R = request.POST.get("resistance")

        if I == "" or R == "":
            result = "Invalid input"
        else:
            try:
                I = float(I)
                R = float(R)
                result = (I ** 2) * R
            except ValueError:
                result = "Invalid input"

    return render(request, 'home.html', {"result": result})
```
# SERVER SIDE PROCESSING:
<img width="1502" height="259" alt="528688939-1ac9e754-6113-4ad0-9fd4-0d4925eefd0c" src="https://github.com/user-attachments/assets/e85e974e-947e-48f1-a45a-ff05841440ce" />

# HOMEPAGE:
<img width="1919" height="1076" alt="528688616-f04f7c2d-d281-428f-af97-a854106e0761" src="https://github.com/user-attachments/assets/61768ce8-d011-4236-85da-37f59d8d1238" />


# RESULT:
<img width="1900" height="1074" alt="528688743-2e693ff2-1873-44ce-8880-063ff6735f90" src="https://github.com/user-attachments/assets/78319b5e-fbd0-4a54-bbfb-b759c3e109ee" />
<img width="1919" height="1079" alt="528688818-16b8cbc9-632e-480a-879c-3c25b1f5efb4" src="https://github.com/user-attachments/assets/8bef3502-ea75-43a6-ab20-30228b2bed01" />


The program for performing server side processing is completed successfully.
