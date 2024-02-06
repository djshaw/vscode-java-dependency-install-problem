# `vscode-java-dependency` Install Problem

`devcontainer.json` defines two vscode extensions: Gradle for Java (`vscjava.vscode-gradle`) and 
Project Manager for Java (`vscjava.vscode-java-dependency`).

```
"extensions": [
    "vscjava.vscode-java-dependency",
    "vscjava.vscode-gradle"
]
```

The Gradle extension is defined to show that at least one extension can be installed and activated 
with an entry in `customizations.vscode.extensions`. The `build.gradle` file (and other support 
files) exist so that the Gradle tab is populated in the activity bar.

## `devcontainer` Start Up Logs

The complete logs for a `devcontainer` build and startup is logged in 
[dev-container-build-log.txt](dev-container-build-log.txt). In particular, we can see that an
install step is executed for the Project Manager for Java extension:

```
[15064 ms] [20:31:02] Installing extension 'vscjava.vscode-java-dependency'...
[15066 ms] [20:31:02] Getting Manifest... vscjava.vscode-java-dependency
[15071 ms] [20:31:02] Installing extension 'vscjava.vscode-gradle'...
[20:31:02] Getting Manifest... vscjava.vscode-gradle
[15224 ms] [20:31:02] Installing extension 'ms-azuretools.vscode-docker'...
[20:31:02] Getting Manifest... ms-azuretools.vscode-docker
[15446 ms] [20:31:02] Installing extension: vscjava.vscode-java-dependency
[15447 ms] [20:31:02] Installing extension: vscjava.vscode-gradle
[15642 ms] [20:31:03] Installing extension: ms-azuretools.vscode-docker
```

However, when the dev container finishes launching, the Java Project tab isn't present in the
Explorer tab.


## Installing Manually

Installing the Project Manager for Java manually, the Java Project tab is populated in the Explorer
tab.  The complete logs for the install is:

```
[467824 ms] [20:38:35] Getting Manifest... vscjava.vscode-java-dependency
[468076 ms] [20:38:35] Installing extension: vscjava.vscode-java-dependency
[470432 ms] [20:38:37] Extension signature is verified: vscjava.vscode-java-dependency
[470475 ms] [20:38:37] Extracted extension to file:///home/vscode/.vscode-server/extensions/vscjava.vscode-java-dependency-0.23.4: vscjava.vscode-java-dependency
[470480 ms] [20:38:37] Renamed to /home/vscode/.vscode-server/extensions/vscjava.vscode-java-dependency-0.23.4
[470482 ms] [20:38:37] Extracting extension completed. vscjava.vscode-java-dependency
[470489 ms] [20:38:37] Extension installed successfully: vscjava.vscode-java-dependency
```
