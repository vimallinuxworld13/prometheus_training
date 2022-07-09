# prometheus_training

engine_daemon_container_states_containers

engine_daemon_container_states_containers{state="running"}

up{region="IN"}

sum ( up{region="IN"} )

# range vector example
node_memory_MemFree_bytes{env="prod"}[10m]

# instant vector example
node_memory_MemFree_bytes{env="prod"}

node_memory_MemFree_bytes{env!="prod"}

process_cpu_seconds_total{job=~"linuxnode.*"}

process_cpu_seconds_total{job!~"linuxnode.*"}

prometheus_http_requests_total{handler=~"/api.*"}

prometheus_http_requests_total{handler=~"/api.*" , code="400"}

prometheus_http_requests_total{handler=~"/api.*" , code="200"}

sum ( prometheus_http_requests_total{handler=~"/api.*" , code="200"} )

sort (prometheus_http_requests_total{handler=~"/api.*" , code="200"}  )

sort_desc (prometheus_http_requests_total{handler=~"/api.*" , code="200"}  )

topk(  3,   sort_desc(prometheus_http_requests_total{handler=~"/api.*" , code="200"}  )   )  

bottomk (  3,   sort_desc(prometheus_http_requests_total{handler=~"/api.*" , code="200"}  )   )  

node_memory_MemFree_bytes / 1024 / 1024

node_cpu_seconds_total{mode="idle"} > 4800

node_cpu_seconds_total{mode="idle"} or  node_cpu_seconds_total{mode="iowait"} 


sum (prometheus_http_requests_total ) by (code)

sum (node_cpu_seconds_total)  by (env, mode)

max ( sum (node_cpu_seconds_total)  by (env, mode) )

rate ( prometheus_http_requests_total[1m] )

rate ( prometheus_http_requests_total{handler=~"/api.*"}[10m] )

rate ( engine_daemon_container_states_containers{state="running"}[2h] )

irate ( prometheus_http_requests_total[1m] )

changes ( process_start_time_seconds{job="dockerplatform1"}[1h] )

changes ( process_start_time_seconds{job="dockerplatform1"}[1h] )

deriv ( process_resident_memory_bytes{job="linuxnode2"}[1h] )

predict_linear ( node_memory_MemFree_bytes{job="linuxnode1"}[1h]  ,   1 * 60 * 60  * 24)  / 1024 / 1024

( time()  - process_start_time_seconds{job="linuxnode1"}  ) / 60 / 60



