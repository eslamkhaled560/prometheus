# Prometheus Lab 1 - Prometheus Basics and Installation

**Presented to:**    
_Mohammed Swelam_    

**Presented by:**   
_Islam Khaled_    

21 July 2023

-----------------------------------------
## 1- What are the different HTTP status codes and explain their meaning?

__- 1xx - Informational__              
The server has received the request and is continuing to process it. The client should wait for further instructions.              
               
__- 2xx - Success__             
The server successfully received, understood, and accepted the client's request.                
           
__- 3xx - Redirection__           
The client will need to take further action to complete the request.           
               
__- 4xx - Client Errors__             
These codes indicate that there was an error with the client's request.             
                    
__- 5xx - Server Errors__          
These codes indicate an error on the server while processing the request.                         

-----------------------------------------
## 2- What database is used by Prometheus?

__TSDB__: custom database for storing and querying time-series data. This database is specifically designed to handle the high volume of time-series data.

-----------------------------------------
## 3- What is the difference between different metrics types ( counter, gauge, histogram)?

__- Counter__: _How many?_          
Counters measure cumulative values, such as the total number of requests served, the number of errors encountered, or the total number of events processed.         
                    
__- Gauge__: _What is the currenr event state?_            
Gauges are used to measure and track fluctuating values, such as the current number of active users, CPU usage, or memory usage.                
                         
__- Histogram:__ _How long?_         
Histograms are used for sampling and observing data distribution over time.

-----------------------------------------
## 4- Install Prometheus on your local host or on a server in any cloud provider.

- AWS Instance

![1](https://github.com/eslamkhaled560/prometheus/assets/54172897/46644275-fbb6-4f54-a0c7-85c0439fbea0)

- Prometheus service status

![2](https://github.com/eslamkhaled560/prometheus/assets/54172897/537141d9-fa01-480e-b421-1b2e3a9e4208)

- Accessing Prometheus UI

![3](https://github.com/eslamkhaled560/prometheus/assets/54172897/8af68373-c162-4eb0-acfc-305b36cb2c64)

-----------------------------------------
## 5- Add any new target to prometheus.yaml file and apply any query on it using promql language. 

- Node exporter service status

![4](https://github.com/eslamkhaled560/prometheus/assets/54172897/1b1f4d3b-c813-4aee-989f-fc39e229d4aa)

- Add node exporter to yaml file

![5](https://github.com/eslamkhaled560/prometheus/assets/54172897/ac553520-2fad-426e-b0c8-f203d64309dd)

- Linux node exporter job

![6](https://github.com/eslamkhaled560/prometheus/assets/54172897/5486ba48-7b87-412a-87e6-2325a904855d)

- The number of CPUs (logical cores) available. (t2.medium)

![7](https://github.com/eslamkhaled560/prometheus/assets/54172897/06ed0624-37fb-4f7f-891e-13de6388bd66)

- Used memory percentage.

![8](https://github.com/eslamkhaled560/prometheus/assets/54172897/f46b481d-38e2-4528-a31a-19643430ccff)

- Used disk percentage

![9](https://github.com/eslamkhaled560/prometheus/assets/54172897/5c091e39-1ebe-4caa-8a3e-9e916ad3d8c3)

-----------------------------------------
