# China area

This project is configured to download/prepare/build a complete Pelias installation for China, and data includes Hong Kong, Macao and Taiwan. For now we modified docker's domestic mirror source, if you need to pull from [DockerHub](https://hub.docker.com/u/pelias), modify [docker-compose.yml](./docker-compose.yml) to remove `docker.1ms.run/`.

# Setup

Please refer to the instructions at <https://github.com/pelias/docker> in order to install and configure your docker environment.

The minimum configuration required in order to run this project are [installing prerequisites](https://github.com/pelias/docker#prerequisites), [install the pelias command](https://github.com/pelias/docker#installing-the-pelias-command) and [configure the environment](https://github.com/pelias/docker#configure-environment).

Please ensure that's all working fine before continuing.

# Run a Build

To run a complete build, execute the following commands:

```bash
pelias compose pull
pelias elastic start
pelias elastic wait
pelias elastic create
pelias download all
pelias prepare all
pelias import all
pelias compose up
```

# Make an Example Query

You can now make queries against your new Pelias build:

<http://localhost:4000/v1/search?text=Chengdu>

# TODO

- [X] Test for correctness and improve documentation.
- [X] Refinement of "disputed areas" not covered by China in whosonfirst.
- [X] Add the correct custom CSV data.
- [ ] Add real CSV data([https://opendata.pku.edu.cn/dataset.xhtml?persistentId=doi:10.18170/DVN/WSXCNM](https://opendata.pku.edu.cn/dataset.xhtml?persistentId=doi:10.18170/DVN/WSXCNM)).
- [ ] Add polyline data of China.
