# Ex.08 Design of Interactive Image Gallery


## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
gallery.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <link rel="stylesheet" href="main.css">
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#gallery">Gallery</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main id="gallery">
        <div class="gallery-container">
            <div class="gallery-item">
                <img src="1.jpg" alt="Image 1">
                <p>DOWNLOADS</p>
            </div>
            <div class="gallery-item">
                <img src="2.jpg" alt="Image 2">
                <p>TELEGRAM IMAGES</p>
            </div>
            <div class="gallery-item">
                <img src="3.jpg" alt="Image 3">
                <p>CAMERA IMAGES</p>
            </div>
            <div class="gallery-item">
                <img src="4.jpg" alt="Image 4">
                <p>DOCUMENTS</p>
            </div>
            <div class="gallery-item">
                <img src="5.png" alt="Image 5">
                <p>SCREENSHOTS</p>
            </div>
            <div class="gallery-item">
                <img src="6.jpg" alt="Image 6">
                <p>INSTAGRAM IMAGES</p>
            </div>
            <div class="gallery-item">
                <img src="7.jpg" alt="Image 7">
                <p>WHATSAPP IMAGES</p>
            </div>
            <div class="gallery-item">
                <img src="8.jpeg" alt="Image 8">
                <p>WINDOWS IMAGES</p>
            </div>
            <!-- Add more images as needed -->
        </div>
    </main>

    <footer>
        <p>&copy; 2024 Your Website</p>
    </footer>
</body>
</html>
```
```
main.css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    padding: 10px 0;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
}

nav ul li {
    margin: 0 15px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

.gallery-container {
    display: grid;
    grid-template-columns: repeat(7, 1fr); /* Adjust the columns as needed */
    gap: 10px;
    padding: 20px;
}

.gallery-item {
    text-align: center;
}

.gallery-item img {
    width: 100%;
    height: auto;
    border-radius: 8px;
}

.gallery-item p {
    margin: 5px 0 0;
    font-size: 0.9em;
    color: #555;
}

footer {
    text-align: center;
    padding: 10px 0;
    background-color: #f1f1f1;
    margin-top: 20px;
}
```
```
models.py
from django.db import models

class Image(models.Model):
    title = models.CharField(max_length=100)
    image = models.ImageField(upload_to='images/')

    def __str__(self):
        return self.title
```
```
views.py
from django.shortcuts import render
from .models import Image

def gallery_view(request):
    images = Image.objects.all()
    return render(request, 'gallery.html', {'images': images})
```
```
urls.py
from django.urls import path
from yuviapp.views import gallery_view

urlpatterns = [
    path('', gallery_view, name='gallery'),
]
```
## OUTPUT:
![Screenshot 2024-11-07 232116](https://github.com/user-attachments/assets/026addd2-4628-437a-af2c-4e50a601b20b)


## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
