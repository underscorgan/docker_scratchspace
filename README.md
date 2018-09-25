# docker_scratchspace
miscellaneous dockerfiles

## windows_volume_mounting

Running on Windows 10 Pro, Version 1709, OS Build 16299.665. On Azure with Hyper-V support, using LCOW.

### error
```
C:\Users\puppet\test> docker run -it --rm -v test:/srv/ underscorgan/alpine:volume-test
C:\Program Files\docker\docker.exe: Error response from daemon: container 5c03d327e4eff8fbc5cf9d79309d3ffac9daf9fb453a26bf2f4c240169081efb encountered an error during CreateContainer: failure in a Windows system call: The object already exists. (0x1392) extra info: {"SystemType":"container","Name":"5c03d327e4eff8fbc5cf9d79309d3ffac9daf9fb453a26bf2f4c240169081efb","Owner":"docker","LayerFolderPath":"C:\\ProgramData\\docker\\lcow\\5c03d327e4eff8fbc5cf9d79309d3ffac9daf9fb453a26bf2f4c240169081efb","Layers":[{"ID":"eeff4893-55b5-5576-aa05-9e7592905d63","Path":"C:\\ProgramData\\docker\\lcow\\717873d290e6a45d26cc7b8a735126d9fb7704be6a3cc71a994481ad4c03b4e7\\layer.vhd"}],"MappedDirectories":[{"HostPath":"C:\\ProgramData\\docker\\volumes\\test\\_data","ContainerPath":"/tmp/gcs/5c03d327e4eff8fbc5cf9d79309d3ffac9daf9fb453a26bf2f4c240169081efb/binds/srv","ReadOnly":false,"BandwidthMaximum":0,"IOPSMaximum":0,"CreateInUtilityVM":true},{"HostPath":"C:\\ProgramData\\docker\\volumes\\93c9259e44e22f586dd51e0bf432225196c4dc724dd4766d65d8f0533ed56495\\_data","ContainerPath":"/tmp/gcs/5c03d327e4eff8fbc5cf9d79309d3ffac9daf9fb453a26bf2f4c240169081efb/binds/srv","ReadOnly":false,"BandwidthMaximum":0,"IOPSMaximum":0,"CreateInUtilityVM":true}],"HvPartition":true,"EndpointList":["5f45a7c8-9ee6-4307-881c-821ac22e90d4"],"HvRuntime":{"ImagePath":"C:\\Program Files\\Linux Containers","LinuxInitrdFile":"initrd.img","LinuxKernelFile":"kernel"},"AllowUnqualifiedDNSQuery":true,"ContainerType":"linux","TerminateOnLastHandleClosed":true}.
```

### docker version
```
 C:\Users\puppet\test> docker version
 Client:
 Version:           master-dockerproject-2018-09-03
 API version:       1.39
 Go version:        go1.10.4
 Git commit:        3ea56aa0
 Built:             Mon Sep  3 23:53:23 2018
 OS/Arch:           windows/amd64
 Experimental:      false

 Server:
 Engine:
 Version:          master-dockerproject-2018-09-03
 API version:      1.39 (minimum version 1.24)
 Go version:       go1.10.4
 Git commit:       8af9176
 Built:            Tue Sep  4 00:02:00 2018
 OS/Arch:          windows/amd64
 Experimental:     true
```

### docker info 
```
 C:\Users\puppet\test> docker info
Containers: 0
 Running: 0
 Paused: 0
 Stopped: 0
Images: 83
Server Version: master-dockerproject-2018-09-03
Storage Driver: windowsfilter (windows) lcow (linux)
 Windows:
 LCOW:
Logging Driver: json-file
Plugins:
 Volume: local
 Network: ics l2bridge l2tunnel nat null overlay transparent
 Log: awslogs etwlogs fluentd gcplogs gelf json-file local logentries splunk syslog
Swarm: inactive
Default Isolation: hyperv
Kernel Version: 10.0 16299 (16299.637.amd64fre.rs3_release_svc.180808-1748)
Operating System: Windows 10 Pro Version 1709 (OS Build 16299.665)
OSType: windows
Architecture: x86_64
CPUs: 4
Total Memory: 16GiB
Name: pupperware
ID: VQWA:Y5TW:RNVF:GBSU:JKSH:LLAX:IHSR:G465:7OEH:3EJ3:7JJ3:CWRT
Docker Root Dir: C:\ProgramData\docker
Debug Mode (client): false
Debug Mode (server): false
Registry: https://index.docker.io/v1/
Labels:
Experimental: true
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
```


