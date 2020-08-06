# Cloud Project to Collect Statistical Data from TIBCO Substation

This project collects statistical information published by TIBCO Substation and displays on a Real-time Dashboard with historical data do analysis.

## Products and Versions (Licenses for the products are not included on this project)
  * TIBCO BusinessWorks Container Edition 2.5.3
  * TIBCO Enterprise Message Service 8.5.1 (Client)
  * TIBCO Spotfire Server 10.10.0
  * TIBCO Spotfire Analyst 10.10.0
  * TIBCO Streaming 10.6.0
  * Docker
  * PostgreSQL

## Prerequisites
  * Access to [TIBCO® eDelivery](https://edelivery.tibco.com)
  * [Docker](https://docs.docker.com/engine/installation/)
  * [Docker Compose v3 or above](https://docs.docker.com/compose/install/)
  * [Postres for Docker](https://hub.docker.com/_/postgres)
  * (Optional)BWCE Base Docker Image - [Github Project with instructions](https://github.com/TIBCOSoftware/bwce-docker)

## Download TIBCO Products
  * Download the appropriate TIBCO Products from [TIBCO® eDelivery](https://edelivery.tibco.com)
    * [TIBCO BusinessWorks Container Edition 2.5.3 artifacts](https://edelivery.tibco.com/storefront/eval/tibco-businessworks-container-edition/prod11654.html). It contains TIBCO BusinessWorks Container Edition runtime (`bwce-runtime-<version>.zip`).
    * [TIBCO Enterprise Message Service 8.5.1 (Client)](https://edelivery.tibco.com/storefront/eval/tibco-enterprise-message-service-client/prod10930.html) Linux Version
    * [TIBCO Spotfire Server 10.10.0](https://edelivery.tibco.com/storefront/eval/tibco-spotfire-server/prod10256.html) Linux Version
    * [TIBCO Spotfire Analyst](https://edelivery.tibco.com/storefront/eval/tibco-spotfire-analyst/prod10204.html). That one is installed on host machine, choose the best option to you.
    * [TIBCO Streaming 10.6.0](https://edelivery.tibco.com/storefront/eval/tibco-streaming/prod11980.html) Linux Version

## Installation
  * **Create BWCE base image. ONLY IF YOU DON'T HAVE YET.**
    * If you have the TIBCO BusinessWorks Container Edition installed on host machine:
      * Go to `<BWCE_HOME>/docker`
      * Copy the `bwce-runtime-<version>.zip` file to the `<BWCE_HOME>/docker/resources/bwce-runtime` folder
      * Open a command terminal and execute the following command from the `<BWCE_HOME>/docker` folder:
        `docker build -t tibco/bwce:latest .`
      * You can check if the image was created using the following command: `docker images`
    * If you DON'T have the TIBCO BusinessWorks Container Edition installed on host machine. There is a GitHub project that you can download and create the base iamge:
      * Go to [Github - bwce-docker Project](https://github.com/TIBCOSoftware/bwce-docker)
      * Follow the instructions provided to create the base image.

  * **Install EMS Drivers**
    * Copy the TIBCO Enterprise Message Service OSGi client libraries from `<EMS_HOME>/components/1.0/plugins` to `<THIS_PROJECT_LOCATION>/resources/ems`

