# docker-build-scripts
Build pipeline scripts for docker containers
`
docker-save-ftp 192.168.2.1 username password "containerimage" destination
`

## Moving files manually

### Docker Build, export and move
`docker build -t amaurer/alarmdecoder:0.1 .`
`docker save -o alarmdecoder.dkrsv amaurer/alarmdecoder:0.1`
`scp alarmdecoder.dkrsv pi@192.168.2.3:/home/pi/alarmdecoder.dkrsv`

### Docker Import with Dockerfile
`docker load -i alarmdecoder.dkrsv`

### One Line Export
`docker build -t amaurer/alarmdecoder:0.2 . && docker save -o alarmdecoder.dkrsv amaurer/alarmdecoder:0.2 && scp alarmdecoder.dkrsv pi@192.168.2.3:/home/pi/alarmdecoder.dkrsv`
