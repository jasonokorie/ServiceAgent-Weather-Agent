# ServiceAgent-Weather-Agent
Here's a n8n workflow utilizing OpenWeatherAPI to send emails

## Weather Agent – n8n Workflow

### Overview
This workflow runs daily to fetch weather data, generate alerts, store logs in Supabase, and send an email summary.

<img width="1148" height="477" alt="image" src="https://github.com/user-attachments/assets/6af9141f-bd89-4d0b-9d62-1d57be0881cf" />


### API Setup
- Weather API: OpenWeatherMap
- Endpoint: /data/2.5/weather
- Units configurable via Config node
- In the config node add the OpenWeather API Key to the field 'appid'

### Supabase
- Table: weather_logs
- Inserted via REST API
- Fields include temperature, humidity, wind speed, alert type, summary, raw response

### Email
- SMTP configured via n8n credentials
- Sends daily HTML email with weather summary

### Running the Workflow
1. Import the JSON into n8n
2. Configure API keys and SMTP credentials
3. Set city + units in Config node
4. Activate workflow
