# Ex.08 Design of Interactive Image Gallery
# Date:
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
urls.py

from django.contrib import admin
from django.urls import path
from galleryapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.gallery, name='gallery'),
]
views.py

from django.shortcuts import render

def gallery(request):
    return render(request, 'gal.html')
gal.html

{% load static %}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Image Gallery</title>

    <style>
        body{
            margin:0;
            background: linear-gradient(to right, #d4f1f9, #d9f7e8);
            font-family: Georgia, serif;
        }

        h1{
            text-align:center;
            margin:30px 0;
            letter-spacing:3px;
        }

        /* GALLERY FLEX */
        .gallery{
            display:flex;
            flex-wrap:wrap;
            justify-content:center;
            gap:40px;
            padding:40px;
            max-width:1200px;
            margin:auto;
        }

        .gallery a{
            text-decoration:none;
        }

        .gallery img{
            width:320px;
            height:230px;
            object-fit:cover;
            border-radius:18px;
            box-shadow:0 12px 22px rgba(0,0,0,0.35);
            transition: transform 0.35s ease, box-shadow 0.35s ease;
            cursor:pointer;
        }

        .gallery img:hover{
            transform: scale(1.2);
            box-shadow:0 18px 40px rgba(0,0,0,0.55);
            z-index:10;
        }

        /* POPUP OVERLAY */
        .Photo{
            position:fixed;
            top:0;
            left:0;
            width:100%;
            height:100%;
            background:rgba(0,0,0,0.85);
            display:none;
            justify-content:center;
            align-items:center;
            z-index:100;
        }

        .Photo img{
            max-width:90%;
            max-height:85%;
            border-radius:15px;
            box-shadow:0 0 30px black;
        }

        .Photo:target{
            display:flex;
        }

        .close{
            position:absolute;
            top:20px;
            right:30px;
            font-size:40px;
            color:white;
            text-decoration:none;
            font-weight:bold;
        }
    </style>
</head>

<body>

<h1>IMAGE GALLERY</h1>

<div class="gallery">
    <a href="#img1"><img src="{% static 'pic1.jpg' %}"></a>
    <a href="#img2"><img src="{% static 'pic2.jpg' %}"></a>
    <a href="#img3"><img src="{% static 'pic3.jpg' %}"></a>
    <a href="#img4"><img src="{% static 'pic4.jpg' %}"></a>
    <a href="#img5"><img src="{% static 'pic5.jpg' %}"></a>
    <a href="#img6"><img src="{% static 'pic6.jpg' %}"></a>
</div>

<!-- POPUP IMAGES -->
<div class="Photo" id="img1">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic1.jpg' %}">
</div>

<div class="Photo" id="img2">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic2.jpg' %}">
</div>

<div class="Photo" id="img3">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic3.jpg' %}">
</div>

<div class="Photo" id="img4">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic4.jpg' %}">
</div>

<div class="Photo" id="img5">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic5.jpg' %}">
</div>

<div class="Photo" id="img6">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'pic6.jpg' %}">
</div>

</body>
</html>
```
# OUTPUT:
<img width="1034" height="527" alt="gallary" src="https://github.com/user-attachments/assets/a92710aa-4f7c-48b8-8ea6-a50023245a41" />

<img width="1010" height="495" alt="gallary (2)" src="https://github.com/user-attachments/assets/2addecd0-7be8-4d11-86fd-221682ab89c7" />


# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
