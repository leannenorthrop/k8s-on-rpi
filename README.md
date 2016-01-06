<!---
 Copyright 2015 Arjen Wassink

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
--->

Kubernetes on Raspberry PI
==========================

Fork of awassink's k8s-on-rpi, interested parties may find https://github.com/luxas/kubernetes-on-arm more useful. 

To use:

* Update rootfs/etc/kubernetes/k8s.conf with suitable IP address pointing to master node's IP address
* Ensure Docker is installed and working (able to run images and report on them)
* Execute install-k8s-master.sh on master node
* Execute install-k8s-worker.sh on one or more worker nodes

This fork contains a fix to work on Arch Linux Arm with latest systemd which requires Docker daemons to use --exec-opt native.cgroupdriver=cgroupfs option. At time of writing Docker 1.9.1 on Arch Linux Arm requires building from source against Go 1.4 due to issue of currently packaged Docker executable compiled against 1.5 throwing errors.

