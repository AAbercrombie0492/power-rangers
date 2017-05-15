# paretoPOWER
paretoPOWER was built to address the DSM Same Sun More Power challenge No. 1. It is a hybrid visualization and data analytics platform to assess the financial benefits of a materials solution - such as a coating with anti-reflective and anti-soiling properties - on an existing PV system. We’ve developed four components: a map visualization platform, a soiling estimator, an O&M cost calculator, and financial model that together will help DSM determine the financial viability of their material solution by market through LCOE and payback period analytics. This tool can also be used to determine the tipping point within the lifespan of an existing PV system where a materials coating could result in positive financial benefits.

## How paretoPOWER Works
### WEB APP
<a target="_blank" href="http://198.199.115.55/paretopower/">Check it out!</a>
### MAP AND DATA VISUALIZATION
In this tool you can toggle between maps of climate zones, average soiling rates, and estimated solar yield (from Solar GIS data). Our current map is accurate down to the county level in the United States. The map portion of the tool provides a visual guide to the user on areas of high solar potential as well as climate regions (by county) in need of a materials solution to reduce the rate of soiling.
### DYNAMIC SOILING RATES AND O&M COST CALCULATIONS
Pulling in weather files, rainfall data, and climate region characteristics, the soiling rates as well as and washing frequencies are calculated to determine the overall impact on solar production performance by region. Soiling thresholds trigger washing events, which are fed as inputs into our O&M cost estimation model, which dynamically scales by system size and includes analytics around deviations in O&M costs.
### LCOE AND PAYBACK PERIOD ANALYTICS
The user can define the PV system with factors such as size, total life span, location, estimated coating material cost, estimated impact on soiling rates by the coating material, as well as the year of application. The tool run analytics and presents an economic analysis in terms of LCOE and payback period to determine materials feasibility.

The LCOE of the PV install has been calculated for three different install and O&M cost scenarios (high, average and low) for variations of PV system performance with and without soiling as well as with and without coating. These calculations account for the costs associated with the application and purchase of the coating materials, as well as the adjustment in solar yield due to soiling rates, system cleaning frequency, and reduction in O&M costs across the remaining lifespan of the system. It also calculates the estimated payback period associated with implementing this materials solution.

### Future Work
Currently, this tool has been optimized for the United States and should be expanded to include international climate zones, weather data, and solar yield to assess the financial viability of coating materials on a global scale. Additional features and refinements needed in our tool include: expanding rainfall profiles through an API, calculating the yield losses on an hourly basis, and refining build-up rates per climate down to particle type. We also would like to investigate the change in the effectiveness of the applied material over time on solar performance.

A future expansion of this tool is to automatically identify PV installs via a Convolutional Neural Network trained on aerial imagery and, based on climate zones and soiling rates, determine whether there is a potential business opportunity. This would enable DSM to identify and target the sales of their materials towards existing PV installs that have a high probability of financial benefit through O&M cost reduction and increased PV production output.

## Setup
This is if you want to run the web app on a local server. You can also just view the <a target="_blank" href="http://198.199.115.55/paretopower/">web app here.</a>

Make sure to have [nodejs](https://nodejs.org/en/download/) installed.

### Set up backend
*From project root:*
```sh
pip install -r requirements.txt
```

### Set up frontend
*From project root:*
```sh
npm install -g bower
cd app/static && bower install
```

## Start the server
*From project root:*
```sh
python run.py runapp --debug --port=8888
```
The port number is arbitrary. It just needs to not already be in use. 

Once the server is running, visit <http://localhost:8888/index.html> in your browser.
