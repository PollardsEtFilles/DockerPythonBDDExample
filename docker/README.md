
## Install Docker
Download and install docker for mac
https://docs.docker.com/docker-for-mac/install/#download-docker-for-mac
choose stable
https://download.docker.com/mac/stable/Docker.dmg

Installed the download in the usual way....

## To build the 'pef' images
```
./build-python3.sh
./build-jupyter-scipy.sh
```

## Image Contents
Both images are unique but have commonn libraries in requirements-test.txt
which includes:-
* pytest
* pytest-bdd
* behave
* behave-pytest

## Running the Images
#### To start jupyter
`./jupyter-scipy.sh`

#### To run interactive python3 shell
`./jupyter-scipy.sh python`

#### Or python2
`./jupyter-scipy.sh python2`

#### To see what modules are available
`./jupyter-scipy.sh python py/modules.py`

#### To start bash shell
`./jupyter-scipy.sh bash`

## To start python3.sh

#### python3
`./python3.sh`

#### run pytests in current dir
`./python3.sh pytest`

#### To see what modules are available
`./python3.sh python py/modules.py`

#### bash
`./python3.sh bash`


## Notes

We have to build the docker image in this dir to take advantage of common files such 
as requirements-test.txt Python dependency file, but we reference the Docker file 
in a sub directory with the `-f` option.
This is needed because Docker files cannot use resources in the parent directory
so `ADD ../requirements-test.txt ...` is not allowed on the Docker file.

## References
https://circleci.com/blog/it-really-is-the-future/
https://circleci.com/blog/its-the-future/
http://hokstad.com/docker/patterns
https://docs.docker.com
https://docs.continuum.io/anaconda/pkg-docs
http://docs.projectatomic.io/container-best-practices/
https://lebkowski.name/docker-volumes/
https://github.com/geerlingguy/ansible-role-docker

### Security
https://medium.com/@mccode/processes-in-containers-should-not-run-as-root-2feae3f0df3b
https://www.infoworld.com/article/3154711/security/8-docker-security-rules-to-live-by.html
https://sysdig.com/blog/7-docker-security-vulnerabilities/
https://docs.docker.com/engine/installation/linux/linux-postinstall/
