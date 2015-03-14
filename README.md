# Pyointillism
Pyointillism is a python script that takes an image and uses a genetic algorithm to evolve a closer and closer representation of it over time. We start with a random collection of dots in random locations, and all of the children slightly change some of these dots. We then compare the image drawn from these dots to the original, and the one with the smallest difference survives. It is named after pointillism, the art style of drawing images using only dots, as the result ends up looking similar to a painting in that style.

Initially basic shapes appear, but nothing discernable. These are the best performing organisms at generations 100,200,300,400, and 500. By the end you may be able to guess at the image.<br>
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/100.png" title="100 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/200.png" title="200 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/300.png" title="300 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/400.png" title="400 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/500.png" title="500 generations">
<br>

In images 1000, 2500, 5000, 7500, and 10000, things become much clearer.<br>
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/1000.png" title="1000 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/2500.png" title="2500 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/5000.png" title="5000 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/7500.png" title="7500 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/10000.png" title="10000 generations">
<br>

Finally at 20000,30000, and 40000, we flesh out some of the details. The original reference image is shown at the end - my fitness function shows that the 40000th generation and the reference image differ by 4.49%.<br>
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/20000.png" title="20000 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/30000.png" title="30000 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/40000.png" title="40000 generations">
<img width="150" height="auto" src="http://scholtek.com/pictures/pyointillism/reference.png" title="Reference image">

#Running Pyointillism
The code is stored in a single python script. Download pyointillism.py, and install the dependencies (pil and numpy) using pip. The script will run from the beginning with no arguments, but it expects to find a file named "reference.png" in the same directory that it is running from. It will then create a results/ folder, and output the best performing image every 100 generations, along with a save file to restart from that point (start from where you left off by passing it in with the -s argument).

```bash
python pyointillism.py [-t threads] [-s save file]
```
    -t                               number of threads to use for processing (defaults to all but 1)
    -s                               location of save file to start from
    
#Purpose
Obviously anything produced by this algorithm can be done more quickly and easily with some image manipulation magic. This was created as sort of a simple genetic algorithm example - the code is well commented with general genetic algorithm information and I hope someone can learn something from it (or show me some things I need to learn).
