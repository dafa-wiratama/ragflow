```shell
clear;
export COMPOSE_PROFILES=elasticsearch,kibana
clear;docker compose -f docker/docker-compose-base.yml up -d
```

```shell
source .venv/bin/activate                                
export PYTHONPATH=$(pwd)
JEMALLOC_PATH=$(pkg-config --variable=libdir jemalloc)/libjemalloc.so;
LD_PRELOAD=$JEMALLOC_PATH python rag/svr/task_executor.py 1;
```

```shell
source .venv/bin/activate                                
export PYTHONPATH=$(pwd)
python api/ragflow_server.py;
```
