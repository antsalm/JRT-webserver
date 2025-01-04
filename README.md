[Joel Real Timing](https://www.joel-real-timing.com/index_en.html) server in a container to be ran in a Raspberry Pi (ARM64).

Raspberry Pi 3b has been sufficient to run this container.

**Prerequisites** Working Docker and Docker compose setup. Knowhow how to dump the **_all_** server files from JRT.

How to use this:
1. Clone the contents and folder structure from Repo. Or download as ZIP from top right: Green CODE button -> Download ZIP.
2. Put folders on `/docker/JRT-webserver/` on the Raspberry Pi (or be prepared to adjust the folder locations in `docker-compose.yml`)
3. Dump the exported files from your JRT to `build/_files_to_export_on_webserver/`
4. Add any other stuff you want to be copied inside the image to `build/html-and-images/`
5. In `build/` folder; Build image with command: `sudo docker image build -t jrt-webserver-http-php-8.4.2 .`

   ...Note: **.** is part of the command at the end.
   
6. ..Wait that the image is built.
7. Adjust the port `8080` to something else, if you desire so, on `docker-compose.yml`
8. If you have reverse proxy, update the IP on `apache2/remoteip.conf`
9. Navigate to `/docker/JRT-webserver/` or the folder with `docker-compose.yml`. Start the container with command `sudo docker compose up -d`
10. Navigate to `http://<pi-ip-address>:<port>/timing.html` (Note, there is no `index.html` on `_files_to_export_on_webserver`, but I created one fancy example for you.)

To keep this up to date. You have to rebuild the image with new set of _files_to_export_on_webserver when Joel updates his Timing software.
