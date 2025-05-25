# ArduPilot Fork
## Prerequisites
Make sure you have Vcxsrv installed.  When launching, click next until you see 'Extra Settings'.  Be sure to disable access control.

Dockerfile is set up to have everything you need to build.  Useful aliases below.

```
alias ardush='docker run --rm -it --network host -v $PWD:/ardupilot ardupilot-dev bash'
alias arduc='docker run --rm -it --network host -v $PWD:/ardupilot ardupilot-dev ./waf configure --board=sitl'
alias ardub='docker run --rm -it --network host -v $PWD:/ardupilot ardupilot-dev ./waf plane'
alias sitl='docker run --rm -it --network host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v $PWD:/ardupilot ardupilot-dev sim_vehicle.py -v plane --console --map -w'
```

# SITL Examples
## Takeoff
```bash
# Load the waypoints
wp load Tools/autotest/Generic_Missions/CMAC-circuit.txt
# Send waypoints to the platform
wp list
# Set the platforms mode to AUTO
mode auto
# Arm the platforms throttle (will takeoff)
arm throttle
```
