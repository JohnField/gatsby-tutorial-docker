# gatsby-tutorial-docker

A dockerized environment for Gatsby; specifically the [Gatsby tutorial](https://www.gatsbyjs.org/tutorial/) but probably usable for other setups.

The `.projects` directory can contain one or more Gatsby projects, with source control etc. independent of this container.

To use a project, set a `GATSBY_PROJECT` envirionment variable in either an [.env file](https://docs.docker.com/compose/environment-variables/) or manually, e.g.
``GATSBY_PROJECT=hello-world docker-compose up``

Acting on the container **acts in the context of GATSBY_PROJECT**, e.g. ``docker exec gatsby-container yarn run build`` runs build in the project, in the container.
Can perform other arbitary actions in the container, e.g.
* Use a starter - ``docker exec gatsby-container gatsby new hello-world https://github.com/gatsbyjs/gatsby-starter-hello-world`` - use a starter
* [Deploy to surge](https://www.gatsbyjs.org/tutorial/part-one/#deploying-a-gatsby-site) - ``docker exec -it gatsby-container surge public/ DOMAIN.surge.sh`
Or act on the container itself with e.g.
* ``docker exec -it gatsby-container bash``
* ``cd /gatsby-container``
* ``...``


