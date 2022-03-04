# garage+runai



This repo contains the code of "garage docker" based on the garage code [repository](https://github.com/rlworkgroup/garage) verion 2020.9.0

[Garage docs](https://garage.readthedocs.io/en/latest/)


## Installation of the docker
- Install the docker using [this](https://docs.docker.com/engine/install/ubuntu/). guide


## Installation of the runai
- start from [this](https://icitdocs.epfl.ch/display/clusterdocs/Getting+Started+with+RunAI+SAML) guide for installing and configuring.
- Now you can send a job ( image ) to the cluster to be executed.
- for example you can submit the custom garage image ( which we provided to make an ssh to) like this:
`submit [your job name] -i sadegh97khorasani/runai-ssh-garage:latest --interactive  --service-type=nodeport --port 31170:22 -v /mnt/nfs_share/sadegh:/root/Data
`
- After submiting the job, wait for it to get status of "Running". Then you can make an ssh to the node address ( which you can find in the description of the job ) and port 31170.

* * *

### Other useful commands:
`runai describe job [your job name] -p ban`

`runai delete [your job name]`

`runai list jobs`


### Main code is in Dockerfile in these directories:
`SGDH.py`: the implementation of our algorithm that uses our optimizer in garage/src/garage/torch/algos/.

`SGDHessOptimizer.py`: the implementation of our optimizer in garage/src/garage/torch/optimizers/. 




