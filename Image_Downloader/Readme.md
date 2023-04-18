# Uses DuckDuckGo API to download images


 ### I am using the DuckDuckGo API to download images for my project. Downloaded 100 images of two classes - chose Anteater and Capibara as my class.

### import using the following:
```python
import DuckDuckGoImages as ddg
```
and then you can search and download images from DuckDuckGo using:
```python
ddg.download('kittens')
```
The above command will search for the query phrase ```kittens```, and then will try to download the list of image urls into the current folder.  
Each downloaded image will have a randomic UUIDv4 name.  

### For Reference : https://github.com/JorgePoblete/DuckDuckGoImages
Above usage text is from the original repo.

 
# Pipeline:
1. Download images from DuckDuckGo using the DuckDuckGo_Download.py script.
2. Using the Rename_Images.py script, rename the images to the class name. Rename_Images.py will replace original images with renamed images.
