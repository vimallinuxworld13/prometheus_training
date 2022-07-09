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


