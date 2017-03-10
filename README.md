# ReFindit #

ReFindit is a bibliographic references search engine that brings together information from different sources and builds services on top of the unified data.

Start finding now at [ReFindit.org](http://refindit.org).


![](https://raw.github.com/pensoft/refindit/master/client/i/refindit-architecture.png)


## Requirements ##

1. Node.js
2. Active internet connection

## Installation ##

1. Install <a href="http://nodejs.org/download/">Node.js</a>
2. `git clone http://github.com/pensoft/refindit && cd refindit`
3. `node app.js`
4. In your browser, go to [http://localhost:5000](http://localhost:5000)

## Docker ##

The following is based in part on [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/). After creating Dockerfile:

1. cd to repository directory
2. Build the image `docker build -t rdmpage/refindit .` (note the “.” at the end of the command).
3. To run on local machine `docker run -p 5000:5000 -d rdmpage/refindit`
4. Use `docker ps` to get container id
5. To view get IP address of docker on local machine `docker-machine ip default` (e.g. http://192.168.99.100 )
6. Go to that address and view refindit.
7. Login in to Docker `docker login -u <username> -p <password>`
8. Push to Docker Hub `docker push rdmpage/refindit`



## Data sources ##
ReFindit currently supports the following search types:

| Data source   | simple | advanced |
| :------------ |:------:| :-------:|
| [CrossRef](http://crossref.org/)             | ✔      |  ✔       |
| [DataCite](http://datacite.org/)             | ✔      |  ✔       |
| [PubMed](http://www.ncbi.nlm.nih.gov/pubmed)             | ✔      |  ✔       |
| [RefBank](http://refbank.org/)             | ✔      |  ✔       |
| [GNUB](http://www.globalnames.org/GNUB "Global Names Usage Bank") (incl. [ZooBank](http://zoobank.org/ "The Official Registry of Zoological Nomenclature"))             | ✔      |          |
| [BHL books](http://www.biodiversitylibrary.org/ "Biodiversity Heritage Library")             |        |  ✔       |
| [BHL items](http://www.biodiversitylibrary.org/ "Biodiversity Heritage Library")             |        |  ✔       |
| [Mendeley](http://www.mendeley.com/)             | ✔      |  ✔       |


Note: Due to the asynchronous nature of the dataflow, the JSON returned by the search service is almost-valid - it consists of several lists concated as strings - [...][...]. See the function [someDBsReady](https://github.com/pensoft/refindit/blob/master/client/client.js#L188) in the reference client implementation for a workaround.

 
### ReFindit is powered by ###

[Node.js](http://nodejs.org/) and [Express](http://expressjs.com/).