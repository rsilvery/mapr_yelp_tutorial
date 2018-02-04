# mapr_yelp_tutorial
The Zeppelin notebook used in the MapR Python blog (insert link later)

Goal: Peruse the Yelp Open Dataset and plot the probability of receiving a particular rating using MatPlotLib,PySpark, SparkSQL, and MapR-DB. Tutorial assumes you’ve already uploaded the JSON dataset from here to your distributed file system into /user/mapr/


Step 1: Create a Python environment and store it to MapR-FS

Detailed steps for doing this with Condas can be found <a href="https://maprdocs.mapr.com/home/Zeppelin/InstallPySparkConda.html?hl=pyspark">here</a>. But the overall process is:
Create a Python environment with Pandas and MatPlotLib 
  conda create -p mapr_yelp_tutorial/ python=2 pandas matplotlib
Zip this directory up from inside the directory:
  cd mapr_yelp_tutorial/
  zip -r mapr_yelp_tutorial.zip ./
Store this to MapR-FS
	hadoop fs -put mapr_yelp_tutorial.zip /user/mapr/python_envs/





