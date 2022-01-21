# <h1 align="center"> Rollbar-agent-exporter </h1>

**Template repository for getting started**

# Description
This tool is used to monitor the state that the rollbar-agent saves as a file. Parameters like inode and pos are public as Gauge which prometheus supports on port :8000 .

# How to run
## config rollbar-agent-exporter.conf
- link ***statefile*** to rollbar-agent state
- setup ***sleep_time***: every sleep_time second it will check the state file of rollbar-agent
```
statefile = /var/cache/rollbar-agent.state

# target time how long to sleep between runs (in seconds). will never be longer than this.
sleep_time = 10
```
## Install
The best way is using virtualenv
- use virtualenv
```
virtualenv rollbar-agent-exporter
source rollbar-agent-exporter/bin/activate
```

- Install package
```
pip install -r ./requirements.txt
```

- Run project
```
python ./rollbar-agent-exporter -c rollbar-agent-exporter.conf
```

Now open http://localhost:8000 and enjoy