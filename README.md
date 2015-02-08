# dh-project-group3
This project is part of a bigger project. This project is not meant as a stand-alone project, as the input needed has to be in a specific format.

## Quick start
Before you start, you need the following:
* folder with annotated chapters as XML files (output group 2a)
* index file (output group 2b)

`java -cp Preface.jar preface.analysis.Preface /path/to/chapters /path/to/index.xml`

## Introduction
This project groups together the precompiled Java library from [this project](https://github.com/daalft/dh-project) needed for data extraction as well as the HTML/CSS/JS skeleton needed for the visualization of the extracted data.

## What happens here
Group 3 is concerned with parsing the data from group 2. We:
* parse the chapter files
  * extract coreferences (Julian)
  * parse the text (David)
* parse the index file (Julian)

This information is then used to extract information about entity what words and entities occur with which entities.

When run, the program generates two files:
* `data.json`
* `more.json`

`data.json` contains information about entity links and entity-word co-occurrences, while `more.json` contains some more, but not as essential information.

The default output folder for these files is `./visual`. After these files have been generated, opening `index.html` in `./visual` will present different visualization layers for the data.

## All about the visualization
### CLOUD VIEW
The first page shows a word cloud based on the 100 most frequent content words in the book (this is not one hundred percent correct. We filter out stop words). The cloud is dynamically generated and changes slightly each time the page is reloaded. The words and the frequencies of the words do not change (*obviously*).

The colors of the words are random and do not convey any meaning. The size of the words vaguely indicate their relative frequency.

### NETWORK VIEW
The next logical step is the network. The network shows which entities co-occur with which other entities. 

The entity graph is zoomeable. It is possible to zoom in and out. The graph is also pan-able. It is possible to drag the graph around. Click and hold anywhere not on/over a node or text and drag.

Clicking on a node in the network graph results in that node being selected for detailed view (see next step). The selected node becomes green. Sometimes it takes more than one click to select a node. The node is selected when it has turned green.

Nodes in the graph are either blue or brown. Brown nodes are nodes that have no children (no words co-occuring with this entity could be extracted under the chosen settings). Blue nodes have children.

### DETAILED VIEW

Either after a node has been selected in the graph or after having chosen an entity from the list and after having clicked on the button, the detailed view page shows some more information about the selected entity.

