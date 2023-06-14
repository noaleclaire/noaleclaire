[![GitHub Streak](http://github-readme-streak-stats.herokuapp.com?user=noaleclaire&theme=transparent&hide_border=true)](https://git.io/streak-stats)
[![Top Langs](https://github-readme-stats-ten-beta-54.vercel.app/api/top-langs/?username=noaleclaire&hide_progress=true&langs_count=10&hide=CMake,Makefile,Smarty,Batchfile)](https://github.com/anuraghazra/github-readme-stats)

# Application Installation Script

This folder contains the ***install.sh*** script, an installation script to install your application and setup the required environment if needed on Debian.

## Launch the installation
###  . ./install.sh [OPTION]
####  [OPTION] :
<pre><code> -se, --setup-env
    Start by setting up the device environment
      Installing:
        - java (see: <a href="#java_jdk_version"><b>JAVA_JDK_VERSION</b></a>)
        - postgresql (see: <a href="#postgresql_version"><b>POSTGRESQL_VERSION</b></a>)
        - nginx
        - maven
        - python
        - flex
        - bison
        - gcc
        - g++
        - make
        - pkg-config
        - libcppunit-dev
        - gnuplot
        - snapd + certbot (optional)(see: <a href="#path_ssl_certificate"><b>PATH_SSL_CERTIFICATE</b></a> & <a href="#path_ssl_certificate_key"><b>PATH_SSL_CERTIFICATE_KEY</b></a>)
      Configuring:
        - nginx with a nginx.conf configuration file in /etc/nginx/
        - nginx with a nginx.service service file in /etc/systemd/system/
        - create the user if it doesn't already exists (see: <a href="#user"><b>USER</b></a>)
    Cf. environment-setup.sh & install-ibex.sh
</code></pre>

## Installation process
#### Steps that will occur during the install.sh script:
      With (-se, --setup-env) OPTION:
        - 1-environment-setup.sh
        - 2-install-ibex.sh

      Then:
        - 3-create-cfg-files.sh
        - 4-create-nginx-configuration-files.sh
        - 5-create-dump-script.sh
        - 6-create-upgrade-script.sh
        - 7-create-application-service.sh

## Configuration file (Cf. values.txt)

A configuration file like the one provides as an example (***values.txt***), is used to define the behavior of the installation script.

#### PAIR FORMAT:
      KEY=VALUE

### The configuration file must contains the following keys:

| KEY NAME | DESCRIPTION | MANDATORY | OPTIONAL |
| :---: | :---: | :---: | :---: |
| **APP_NAME** | Application name | ✔️ |  |
| **ENV_GITHUB** | Github environment name (staging, recette, prod, ...) | ✔️ |  |
| **USER** <a name="user"></a> | User name who will be granted permission on the application setup <br/> If the user doesn't exists it will be created | ✔️ |  |
| **CLIENT_FOLDER** | Folder name where the setup will occur <br /> If the folder doesn't exists it will be created <br/> ***The final folder will be in the form of:*** **CLIENT_FOLDER**/**USER**/**ENV_GITHUB**/**APP_NAME** | ✔️ |  |
| **PATH_APP_JAR** | Path of the jar of the application | ✔️ |  |
| **UPSTREAM_BACK** | Upstream name used in the application configuration file for nginx | ✔️ |  |
| **BACK_PORT** | Application port used in the application configuration file for nginx | ✔️ |  |
| **BACK_SERVER_NAME** | Server name used in the application configuration file for nginx | ✔️ |  |
| **PATH_FRONT_FOLDER** | Path of the front folder used in the application configuration file for nginx | ✔️ |  |
| **DB_NAME** | Database name for postgresql | ✔️ |  |
| **DB_USER_NAME** | User name for the database **DB_NAME** of postgresql | ✔️ |  |
| **DB_USER_PASSWORD** | Password of the user for the database **DB_NAME** of postgresql | ✔️ |  |
| **PATTERN_CRON_DUMP** | **Only with ENV_GITHUB=prod** <br /> Cronjob that will run the script for the dump of the database **DB_NAME** | ✔️ |  |
| **PATTERN_CRON_RESTART_APP** | **Only with ENV_GITHUB=prod** <br /> Cronjob that will restart the application service | ✔️ |  |
| **PATTERN_CRON_DELETE_DUMPS** | **Only with ENV_GITHUB=prod** <br /> Cronjob that will delete dump older than 5 days | ✔️ |  |
| **JAVA_JDK_VERSION** <a name="java_jdk_version"></a> | JDK version *(include JRE)* | ✔️ |  |
| **POSTGRESQL_VERSION** <a name="postgresql_version"></a> | Postgresql version | ✔️ |  |
| **PATH_SSL_CERTIFICATE** <a name="path_ssl_certificate"></a> | Path of the ssl certificate |  | ✔️ <br /> (let's encrypt will be used instead) |
| **PATH_SSL_CERTIFICATE_KEY** <a name="path_ssl_certificate_key"></a> | Path of the ssl key |  | ✔️ <br /> (let's encrypt will be used instead) |
| **PATH_PG_HBA_CONF** | **Only with ENV_GITHUB=prod** <br /> Path of the pg_hba.conf to allow user connecting to the database with a password (md5) <br /> (often present in: /etc/postgresql/${version}/main/pg_hba.conf) |  | ✔️ |

### Connect with me on:
<a href="https://www.linkedin.com/in/noa-leclaire-5907b0265/" target="blank"><img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/linkedin.svg" alt="" height="30" width="40" /></a>
</br>
</br>
</br>
<p align="center">
  <img src="images/DevOps_meme.png" width=350/>
  <img src="images/Heart_emote.png" width=40/>
  <img src="images/DevOps_logo.png" width=240/>
</p>
