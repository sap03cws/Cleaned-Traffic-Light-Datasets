# Cleaned Traffic Light Datasets
Various datasets on traffic light (TL) detection are aggregated and cleaned. They include [ApolloScape](http://data.apollo.auto/?locale=en-us&lang=en), [Bosch Small TL Dataset](https://hci.iwr.uni-heidelberg.de/node/6132/), [WPI TL Dataset](http://computing.wpi.edu/dataset.html), and [Kaggle LISA TL Dataset](https://www.kaggle.com/mbornoe/lisa-traffic-light-dataset/data). 

Copyrights belong to the owners of their respective datasets.

# 0. Data Format
Images can be in RGB or in grayscale. They can be resized, or not. Bounding boxes can be expressed in two pairs of coordinates or in one along with width and height information. Traffic lights can be categorized into three categories (red/yellow/green) or two (go/stop). Directional information on traffic lights can be conveyed, or not. In view of such a diverse range of formatting options, a script is provided to properly retrieve and format the data and their corresponding labels. That said, the general format is as follows:

> /path/to/image/file; WIDTH; HEIGHT; 
"BOUNDING_BOX_ARG_1; BOUNDING_BOX_ARG_2; BOUNDING_BOX_ARG_3; BOUNDING_BOX_ARG_4; TRAFFIC_LIGHT_COLOR ;TRAFFIC_LIGHT_DIRECTION" ; 
"BOUNDING_BOX_ARG_1; BOUNDING_BOX_ARG_2; BOUNDING_BOX_ARG_3; BOUNDING_BOX_ARG_4; TRAFFIC_LIGHT_COLOR ;TRAFFIC_LIGHT_DIRECTION" ;
...

### Example 1

For example, a line in the `.csv` file produced by running `sh gen.sh -if jpg -is 224,224 --anchored --directional` might look like this:

> /home/wching/tld/data/img/0001.jpg;224;224;"101;124;15;35;red;left"

### Example 2

For another example, a line in the `.csv` file produced by running `sh gen.sh -if png -ic 640,640 --bounded --binary --nondirectional` might look like this:

> /home/wching/tld/data/img/0001.png;224;224;"101;124;15;35;red;left"

### Example 3

For one last example, a line in the `.csv` file produced by running `sh gen.sh --no-resize --anchored --ternary` might look like this:

> /home/wching/tld/data/img/0001.jpg;1920;1080;";;;;;"

# 1. Scripts
While this repository is by no means complete, or original, it is intended for rapid evaluation of traffic light detection algorithms. For that purpose, two simple scripts are provided - one that generate the needed dataset, and another that calculates accuracy.

## Generation Script

#### Common Usage

## Evaluation Script

#### filename/file path
#### bounding box
#### traffic light signal

# 2. Functions

#### Bash
#### C
#### Python
#### MATLAB
