# Project of data visualization of Otodom rental offers using Airflow, MongoDB, PowerBI and BeatifulSoup

# Process chart

![Chart of data flow](/img/Flowcharts.png)

Above chart shows flow of data in the project. In first phase of data flow, webscraping from Otodom site is done. It is done using BeautifulSoup and Python. There are few items extracted, including IDs, title, size of flat, district, add date and price. This proccess is orchestrated using Airflow which is running in Docker container. There is DAG in Airflow enveirment which is transfering data from website to MongoDB Atlas instance. 

![Airflow](/img/airflow.png)

In next step data is loaded to Power BI report which shows several things:

- price in each district on map,
- count of ads in each district,
- number of rooms in offers,
- average price of rental offers.

Report also allows to filter things like:

- district,
- size of flat,
- number of rooms
- date of ad addition.

![Power BI](/img/powerbi.png)

# Files

- Dockerfile and docker-compose.yaml - files that allows to use Airflow,
- webscrapping-dag.py - implemented version of webscrapping.py to Airflow/DAG,
- get_data_for_PowerBI.py - custom connector for PowerBI to download data from MongoDB,
- warszawa-dzielnice.geojson - map of Warsaw districts






