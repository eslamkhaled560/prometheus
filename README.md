# Prometheus Lab 2

**Presented to:**    
_Mohammed Swelam_    

**Presented by:**   
_Islam Khaled_    

26 July 2023

-----------------------------------------
## 1- How do I trigger a Prometheus alert?

- Setup and configure AlertManager.             
- Configure the config file on Prometheus so it can talk to the AlertManager.              
- Define alert rules in Prometheus server configuration.                
- Define an alert mechanism in AlertManager to send alerts via Slack and Mail.           

-----------------------------------------
## 2- What is the difference between a node exporter and a MySQL exporter?

__Node Exporter:__ The Node Exporter collects a wide variety of metrics from the host operating system, including CPU usage, memory usage, disk usage, network traffic, and process counts. These metrics can be used to monitor the health and performance of the host operating system and to troubleshoot problems.           

__MySQL Exporter:__ The MySQL Exporter collects metrics from MySQL databases, including queries per second, connections, and memory usage. These metrics can be used to monitor the health and performance of MySQL databases and to troubleshoot problems.

-----------------------------------------
## 3- what is the maximum retention period to save data in Prometheus and how to increase it?

- The default maximum retention period for Prometheus is 15 days. However, we can increase this period by editing the Prometheus configuration file. The relevant setting is storage.tsdb.retention.time. The value of this setting can be specified in days, hours, or minutes.        
- Increasing the maximum retention period will increase the amount of disk space that Prometheus uses. 

-----------------------------------------
## 4- What are the different PromQL data types available in the Prometheus Expression language?

__- Scalar:__ A simple numeric floating point value.            
__- String:__ A simple string value. This data type is currently unused in Prometheus.            
__- Instant vector:__ A set of time series containing a single sample for each time series, all sharing the same timestamp.            
__- Range vector:__ A set of time series containing a range of data points over time for each time series.            

-----------------------------------------
## 5- How To calculate the average request duration over the last 5 minutes from a histogram?

- Calculate the quantile value for the histogram using the histogram_quantile function.               
```  histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le)) ```
- Calculate the average over the range vector.               
``` avg_over_time(histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le)))  ```

-----------------------------------------
## 6- What is Thanos Prometheus?

Thanos is an open-source project that extends Prometheus, a popular time series database. It is designed to tackle some of the challenges faced when operating Prometheus at scale, especially in highly distributed and long-term storage scenarios.       

-----------------------------------------
## 7- What is Promtool and how i can use it?

Promtool is a command-line tool that is used to interact with Prometheus. It can be used to do a variety of things, including:      
__- Querying Prometheus data:__ Promtool can be used to query Prometheus data using PromQL.        
__- Validating Prometheus configuration:__ Promtool can be used to validate Prometheus configuration files.        
__- Generating Prometheus rules:__ Promtool can be used to generate Prometheus rules. This can be useful for creating alerts and notifications based on your Prometheus data.       
__- Testing Prometheus alerts:__ Promtool can be used to test Prometheus alerts.

-----------------------------------------
## 8- What types of Monitoring can be done via Grafana?

__- Infrastructure monitoring:__ Grafana can be used to monitor the performance and availability of infrastructure components such as servers, networks, and storage devices.             
__- Application monitoring:__ Grafana can be used to monitor the performance and availability of applications. This includes monitoring metrics such as CPU usage, memory usage, and database queries.             
__- Log monitoring:__ Grafana can be used to monitor logs from applications and infrastructure components.            
__- Alerting:__ Grafana can be used to create alerts that notify you when certain metrics or events occur.          
__- Dashboards:__ Grafana can be used to create dashboards that display your metrics and logs in a visually appealing way.       
__- Security monitoring:__ Grafana can be used to monitor security metrics such as login attempts, failed logins, and unauthorized access.            
__- Compliance monitoring:__ Grafana can be used to monitor compliance metrics such as the number of security alerts, the number of compliance violations, and the number of audit logs.             
__- DevOps monitoring:__ Grafana can be used to monitor DevOps metrics such as the number of deployments, the number of builds, and the number of test cases.

-----------------------------------------
## 9- Can we see different Servers' CPU comparisons in Grafana?

- Yes, you can see different servers' CPU comparisons in Grafana.
- This query will return the average CPU usage for all of your servers over the last 5 minutes.               
```  rate(node_cpu_seconds_total{mode="idle"}[5m] ```       

-----------------------------------------
