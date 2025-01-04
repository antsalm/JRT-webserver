[Joel Real Timing](https://www.joel-real-timing.com/index_en.html) server in a container to be ran in a Raspberry Pi.
**Prerequisites** Working Docker and Docker compose setup.
1. Clone the contents and folder structure from Repo.
2. Put folders on /docker/JRT-webserver/ on the Raspberry Pi, or be prepared to adjust the folder locations in docker-compose.yml
3. Dump the exported files from your JRT to `/build/_files_to_export_on_webserver`
4. Navigate to /build/ folder and Build image with command: `sudo docker image build -t JRT-webserver-http-php-8.4.2 .`

