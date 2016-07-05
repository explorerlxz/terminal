1. Install imagemagick
2. Using a terminal where the pdf is located:

```
convert -density 150 input.pdf -quality 90 output.png
```

whereby:
- PNG, JPG or (virtually) any other image format can be chosen
- density xxx will set the dpi to xxx (common are 150 and 300)
- quality xxx will set the compression to xxx for PNG, JPG and MIFF file formates (100 means no compression)
- all other options (such as trimming, grayscale, etc) can be viewed on the website of Image Magic.


## Reference
[Convert PDF to Image](http://askubuntu.com/questions/50170/how-to-convert-pdf-to-image/50180)
