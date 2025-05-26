# vultr
Documentation and Provisioning Scripts for Vultr Servers

## Motivation
This repository contains scripts and configuration for deploying the
game PeraPera Quest to a Virtual Private Server (VPS) on
[Vultr](https://www.vultr.com/)

## Configuration and Scripts
`linxuser.crontab` provides a crontab for reloading nginx on a regular
basis, in order to pick up renewed SSL certificates from Let's Encrypt.

`provision-debian12-rootless` is a Startup Script to use on a Debian 12
host that will install necessary system packages, configure SSH keys and
firewall rules, and install Docker in a rootless setup.

`infra` contains the scripts and configuration files to manage the
deployment of PeraPera Quest. The services are described in the file
`docker-compose.yml`, which is a configuration file for container
orchestration using Docker Compose.

`infra/bin` contains numbered scripts to get things set up. One of the
most important is getting an SSL certificate from Let's Encrypt, so that
browsers will know they're reaching the real PeraPera Quest web site.

It also has some general purpose scripts to start and stop the services
using Docker Compose.

`infra/nginx` contains the configuration for nginx, a small web server
that serves the game files to people connecting to the PeraPera Quest
web site. `bootstrap.conf` is used initially to obtain an SSL certificate,
but after that `default.conf` is the main configuration file used in
production for serving up the game via the web site.

## License
Copyright 2025 Patrick Meade.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
