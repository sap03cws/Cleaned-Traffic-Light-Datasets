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

> /home/wching/tld/data/img/0001.jpg;224;224;"101;124;16;36;red;left"

In this case, a JPEG image called 0001.jpg of size 224(W)×224(H) is loaded. There is one traffic light found. It is centered at Cartesian coordinate (101,124); it has a size of 16(W)×36(H); it shows a protected-left-turn signal that's red. (In other words, its upper left corner is at (93,106), and its lower right corner is at (109,142).)

### Example 2

For another example, a line in the `.csv` file produced by running `sh gen.sh -if png -ic 640,640 --bounded --binary --nondirectional` might look like this:

> /home/wching/tld/data/img/0002.png;640;480;"93;106;109;142;green;left";"144;110;158;142;red;round"

In this case, a PNG image called 0002.png of size 640(W)×480(H) is loaded. There are two traffic lights found. The first one has its upper left corner at (93,106) and its lower right corner at (109,142); it shows a protected-left-turn signal that's green. The second one has its upper left corner at (144,110) and its lower right corner at (158,142); it shows a general, round signal that's red. (In other words, one traffic light is centered at (101,124) and has a size of 16(W)×36(H). The other is centered at (151,126) and has a size of 14(W)×32(H).)

### Example 3

For one last example, a line in the `.csv` file produced by running `sh gen.sh --no-resize --anchored --ternary` might look like this:

> /home/wching/tld/data/img/0003.jpg;1920;1080;";;;;;"

In this case, a JPEG image called 0003.jpg of size 1920(W)×1080(H) is loaded. There are no traffic lights found.

# 1. Scripts
While this repository is by no means complete, or original, it is intended for rapid evaluation of traffic light detection algorithms. For that purpose, two simple scripts are provided - one that generate the needed dataset, and another that calculates accuracy.

## Generation Script
This script generates a `.csv` file with a designated number of lines, each conforming to the specified format.

#### Dependency
This script needs `Bash` and `sed` to function.

#### Common Usage

## Evaluation Script

#### Dependency
This script needs `Bash`, `sed`, and `bc` to function.

#### filename/file path
#### bounding box
#### traffic light signal

# 2. Output Saving Functions

#### C
#### Python
#### MATLAB
