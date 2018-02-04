<b>MapR Yelp Tutorial</b>

The Zeppelin notebook used in the MapR Python blog (insert link later)

Goal: Peruse the Yelp Open Dataset and plot the probability of receiving a particular rating using MatPlotLib,PySpark, SparkSQL, and MapR-DB. Tutorial assumes you’ve already uploaded the JSON dataset from <a href="https://maprdocs.mapr.com/home/Zeppelin/InstallPySparkConda.html?hl=pyspark">here</a> to your distributed file system and untarred it into the /user/mapr/ directory.


<b>Step 1</b>: Create a Python environment and store it to MapR-FS

Detailed steps for doing this with Condas can be found <a href="https://maprdocs.mapr.com/home/Zeppelin/InstallPySparkConda.html?hl=pyspark">here</a>. But the overall process is:

1. Create a Python environment with Pandas and MatPlotLib: 
	
       conda create -p mapr_yelp_tutorial/ python=2 pandas matplotlib
  	
2. Zip this directory up from inside the directory:

       cd mapr_yelp_tutorial/
       zip -r mapr_yelp_tutorial.zip ./
  
3. Store this to MapR-FS

       hadoop fs -put mapr_yelp_tutorial.zip /user/mapr/python_envs/

<b>Step 2</b>: Load the MapR Data Science Refinery and specify the Python archive created earlier in the Docker run command or environment variable file:

1. Set the following variable either in the Docker Run command or in the environment variables file you’re using:

       ZEPPELIN_ARCHIVE_PYTHON=/user/mapr/python_envs/mapr_yelp_tutorial.zip
       
2. Log into Zeppelin on specified host and port

3. Download our demo notebook from this repo and import it into Zeppelin


