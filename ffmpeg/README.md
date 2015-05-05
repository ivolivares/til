### Create thumbnails each N seconds from any `file.ext`

    ffmpeg -i <file.ext> -vf fps=1/<N> img%03d.jpg
    
  Example:
  
    ffmpeg -i file.mp4 -vf fps=1/60 img%03d.jpg
