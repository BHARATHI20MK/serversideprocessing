# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Desing your website for calculation using wireframe work

### Step 2:
Then to execute the wireframe work desing use html,css

### Step 3:
Use views.py to execute the coding in serverside

### Step 4:
Mention the path of the website in urls.py

### Step 5:
Publish the website in the given URL


## PROGRAM :
```
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of prism</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body 
{
background-color:cyan;
}
.edge {
width: 1080px;
margin-left: auto;
margin-right: auto;
padding-top: 200px;
padding-left: 300px;
}
.box {
display:block;
border: Thick dashed lime;
width: 500px;
min-height: 300px;
font-size: 20px;
background-color: purple;
}
.formelt{
color: Red;
text-align: center;
margin-top: 5px;
margin-bottom: 5px;
}
h1
{
color: yellow;
text-align: center;
padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of a prism</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Height : <input type="text" name="length" value="{{h}}"></input>(in m)<br/>
</div>
<div class="formelt">
Breadth : <input type="text" name="breadth" value="{{b}}"></input>(in m)<br/>
</div>
<div class="formelt">
<input type="submit" value="Calculate"></input><br/>
</div>
<div class="formelt">
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>
```
### views.py
```from django.shortcuts import render
from django.template  import loader
from django.shortcuts import render
# Create your views here.
def triarea(request):
    context={}
    context['area'] = "0"
    context['l'] = "0"
    context['b'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        h = request.POST.get('length','0')
        b = request.POST.get('breadth','0')
        print('request=',request)
        print('height=',h)
        print('Breadth=',b)
        area = 0.5*int(h) * int(b)
        context['area'] = area
        context['l'] = l
        context['b'] = b
        print('Area=',area)
    return render(request,'myapp/math.html',context)
```
### url.py
```
from django.contrib import admin
from django.urls import path
from myapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofprism/',views.triarea,name="areaofprism"),]
```
## OUTPUT:
![out1](https://github.com/BHARATHI20MK/serversideprocessing/assets/147474125/b3eccbc7-023b-41c8-9d9c-0d98f3e65274)
![out2](https://github.com/BHARATHI20MK/serversideprocessing/assets/147474125/22dcb10a-5dae-4527-93e7-b7cd580bb661)



## Result:
The program is executed successfully.

