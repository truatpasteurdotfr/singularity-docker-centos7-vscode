# singularity-docker-centos7-vscode
vscode singularity container on CentOS-7

- https://code.visualstudio.com/docs/setup/linux
- FAQ: disable telemetry, but YMMV

```
From File > Preferences > Settings, add the following option to disable telemetry reporting, this will silence all telemetry events from the VS Code shell.
"telemetry.enableTelemetry": false
```

or create a $HOME/.config/Code/User/settings.json file containing:
```
// Place your settings in this file to overwrite the default settings
{
    "telemetry.enableTelemetry": false,
}
```

Running:
```
singularity exec -B /run vscode-container.img /usr/bin/code
singularity exec -B /run shub://truatpasteurdotfr/singularity-docker-centos7-vscode /usr/bin/code
```
