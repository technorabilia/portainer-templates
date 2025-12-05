# Portainer App Templates for LinuxServer.io Docker containers
These [Portainer App Templates](https://docs.portainer.io/advanced/app-templates) allow you to easily deploy [LinuxServer.io Docker containers](https://hub.docker.com/u/linuxserver/) using predefined settings.

The templates are automatically generated based on data from the [LinuxServer.io GitHub repositories](https://github.com/linuxserver).

Please keep the following in mind:
- The templates are not supported by LinuxServer.io.
- The templates are generated automatically, so requests to add specific templates cannot be accepted.

## Prerequisites
- A server with Docker installed
- Portainer installed

## Install the templates
1. Start Portainer.
2. Go to **Settings**.
3. Enter the App Templates URL:

```
https://raw.githubusercontent.com/technorabilia/portainer-templates/main/lsio/templates/templates.json
````

4. Click **Save settings**.
5. Navigate to **App Templates** where you will now see the templates.

## Application list
All applications listed [here](https://www.linuxserver.io/our-images) are available as templates.

## How to use the templates
As an example, we will look at the Sonarr template.

Go to **App Templates** and select **Sonarr**.

### Information
Before deploying the container, ensure the volume host directories exist. You can copy the paths shown in Portainer and create the directories if necessary.

You can create the directories via command line:

```bash
mkdir -p /volume1/docker/sonarr/config
mkdir -p /volume1/docker/sonarr/tv
mkdir -p /volume1/docker/sonarr/downloads
````

Alternatively, you can create these directories using your preferred file manager.

### Configuration
Review the configuration settings. If required, adjust:
* Process User ID (`PUID`)
* Process Group ID (`PGID`)
* Timezone (`TZ`)
* Any other environment variables

More information about `PUID` and `PGID` can be found [here](https://docs.linuxserver.io/general/understanding-puid-and-pgid).

### Advanced options
Open **Advanced options** by clicking *+ Show advanced options* and review the port mappings and volume mappings.

### Deploy the container
Once all settings are correct and the volume directories exist, click **Deploy the container** in the Actions section at the bottom of the page.

If the deployment is successful, you will see a **Container successfully created** message in the upper right corner of the screen.

### Custom README
Some applications include a custom README. If special instructions are required, you will see the following notice:

*This container needs special attention. Please check [https://hub.docker.com/r/linuxserver/{{](https://hub.docker.com/r/linuxserver/{{) project_name }} for details.*

Follow the link to learn more about the container's usage requirements.

## Report issues
If you encounter a problem, please report it on the project's [GitHub Issues page](https://github.com/technorabilia/portainer-templates/issues). Issues will be reviewed as soon as possible.

## Considerations
* With the default volume structure recommended by LinuxServer.io, you cannot use hard links. More information is available [here](https://docs.linuxserver.io/images/docker-sonarr#application-setup).
* The scripts are updated daily.

## Credits
A big thank you to [LinuxServer.io](https://www.linuxserver.io/) for their outstanding work. Without their efforts, this project would not be possible.
