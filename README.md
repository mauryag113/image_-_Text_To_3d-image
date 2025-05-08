# image_-_Text_To_3d-image

3D Model Generator Flask App
Hey there! This is a simple Flask app I built to generate 3D models from either a text prompt (like "car" or "cube") or an uploaded image. It renders a preview of the model and lets you download it as an .obj file. The UI is pretty nice thanks to Tailwind CSS.
What It Does

You can type a prompt like "car", "cube", or "sphere" to get a basic 3D model.
Or upload a .jpg or .png image, and it'll turn the silhouette into a 3D model (kinda basic but works).
Shows a preview of the 3D model using Matplotlib.
Lets you download the preview as a .png and the model as an .obj.
Cleans up files after 30 seconds to save space.

Setup

Install Python: Make sure you have Python 3 (I used 3.12). You can get it from python.org.
Install dependencies: Run this in your terminal:pip install flask numpy trimesh matplotlib pillow rembg

Note: rembg might need internet to download its model the first time.
Clone or download this project: Grab the app.py file and put it in a folder.
Run the app:python app.py

It’ll start a server at http://localhost:5000. Open that in your browser.

Usage

Home Page: You’ll see a form with two options:
Upload an image (jpg or png only).
Or type a text prompt (try "car", "cube", or "sphere").


Hit the "Generate" button. It’ll say "Generating..." while it works.
Results Page: You’ll see a preview of the 3D model, plus two buttons to download:
The preview image (.png).
The 3D model (.obj).


There’s also a "Generate Another" link to go back and try again.
Note: Downloads only work for 30 seconds before the files get deleted (to save space).

Stuff to Know

The 3D models are pretty basic. Text prompts just make simple shapes (like a box for "car"). Images get turned into a convex hull with a bit of extrusion.
Rendering uses Matplotlib, so it’s not super fancy but gets the job done. I tried using trimesh rendering before but it crashed on Windows.
The UI uses Tailwind CSS via a CDN. It looks clean and works on mobile too.
Files get deleted after 30 seconds. If you need more time to download, you can tweak the wait variable in the cleanup_later function.

Troubleshooting

App crashes? Check if all dependencies are installed. Also, make sure your system has enough memory (esp. for image processing with rembg).
Downloads not working? Make sure you click the download links within 30 seconds. If the files are gone, just generate again.
Preview looks weird? The model might be too big or small. I scale image-based models down by 0.01—might need tweaking for your images.

TODO

Maybe add more shapes for text prompts.
Could make the image-to-3D better (right now it’s just a convex hull).
Add some error messages to the UI instead of just returning 400 errors.

Let me know if you have any questions! 😄
