# ***Generating a multi-resolution network using UMD campus as an example***
## ***How to download a free map file from OpenStreetMap?***
Before the offical introduction, we first introduce a concept called GNMS. General Travel Network Format Specification(GNMS) is a product of Zephyr Foundation, which aims to advance the field through flexible and efficient support, education, guidance, encouragement, and incubation.
In this berif introduction, we will shown you how to generate a multi-resolution network tamplate by what tools, and use other two tools called path4gmns and DLSIM to realize some basic transportation modeling and simulation fuction in this template. To generate a multi-resolution network tamplate, the first tool you need is a python package called OSM2GMNS, which is is an open-source python package which can help users easily convert networks from OpenStreetMap to .csv files with standard GMNS format for visualization, traffic simulation and planning purpose. For more information, please check  [OSM2GMNS](https://github.com/asu-trans-ai-lab/OSM2GMNS). You can either install it via pip :
```python
pip install osm2gmns
```
Or you can install this package inside your python IDIE, take Pycharm as an example (shown as follow), you can go to->Files->Settings->Python interpreter, and you can install any packages in the right-side window. ![Insatll Path4gmns in Pycharm](https://github.com/YuanzhengLei/YuanzhengLei.GitHub.io/blob/main/1.png)
After you installed the package OSM2GMNS, you can download any map data you want from OpenStreetMap [OSM](https://www.openstreetmap.org/), which is a free, open-source, editable map website that can provide free downloads. From this website, we can easily search for any target like a university or a railway station, in this case, we take university of maryland campus as an example. First, you just need to search for university of maryland in the left side search window, and then you can see a general region, so you can adjust the size of the region that you want to export as a .osm map file. It is noted that only a .osm map file can be directly convert in the GMNS format by this package.![The campus of University of Maryland](https://github.com/YuanzhengLei/YuanzhengLei.GitHub.io/blob/main/2.png)
Then, we can Create a network from map.osm file and consolidate complex intersections by (put the .osm map file in the source folder of the python file !!):
```python
import osm2gmns as og
net = og.getNetFromOSMFile('map.osm')
og.outputNetToCSV(net)  
```
