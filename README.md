# ArduPilot Fork
## Prerequisites
Make sure you have Vcxsrv installed.  When launching, click next until you see 'Extra Settings'.  Be sure to disable access control.

Dockerfile is set up to have everything you need to build.  Useful aliases below.

```
alias arduc='docker run --rm -it -v $PWD:/ardupilot ardupilot-dev ./waf configure --board=sitl'
alias ardub='docker run --rm -it -v $PWD:/ardupilot ardupilot-dev ./waf plane'
alias sitl='docker run --rm -it -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/ardupilot ardupilot-dev sim_vehicle.py -v plane --console --map -w'
```
