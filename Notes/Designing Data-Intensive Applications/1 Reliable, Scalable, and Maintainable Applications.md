3 important characteristics
- Reliability
- Maintainability
- Scalability

#### Reliability
roughly "continue to work correctly even if things go wrong".
Fault-Tolerant - systems which can cope up with faults.

__Fault__ : one component of system deviates from its behaviour
__Failure__ : whole system stops providing the service.

_Motive_ : to prevent faults from becoming failures.

##### Hardware Faults: 
- hard disk crash
- RAM faults

##### Software Faults: 
- Software bug 
- Cascading failures
- Service becoming unresponsive

#### Scalability
Ability to cope up with increased load

##### Loads
- requests per second to web sever
- ratio of reads to writes in db
- number of concurrent users in chatroom
- hit rate on cache

##### Performance
ex: __Response time :__ time between client sending a request and recieving a response

##### Percentiles
get all response time and sort it from low to high, median is the mid point of that list.

__p50:__ half of user requests are served before median time and half after median time

In other words considering a fixed time as threshold, p50 means 50% of requests take less than the threshold time for reponse time.

__p95__ : 95% of requests response times are below the threshold
Similarly p99, p999 (99.9%)

__Tail Latency:__ High percentiles of response times
 
#### Maintainability

- Operability: make it easy for operations teams to keep the system running smoothly
- Simplicity: remove as much complexity as possible
- Evolvability: Easier to make changes in the future
