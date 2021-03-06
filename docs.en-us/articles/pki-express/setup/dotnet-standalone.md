﻿# Standalone installation of .NET Core Runtime

On Linux environments, [PKI Express](../index.md) requires the **.NET Core Runtime**. The recommended way to install it
is described on the installation instructions of PKI Express for each supported distribution.

However, if you cannot add private package feeds to your environments, follow the steps below to perform a standalone installation of the .NET Core Runtime.

> [!NOTE]
> If you Linux distribution is not listed below, please contact us.

## CentOS / Oracle Linux / Fedora

<!--
    Apparently, 2.1 no longer requires doing a `sudo yum install libunwind libicu`:
    https://github.com/dotnet/core/blob/master/release-notes/download-archives/2.1.0-download.md
-->

Download the .NET Core Runtime standalone package, extract to the destination directory and create a symbolic link for the executable:

```sh
curl -O https://download.microsoft.com/download/9/1/7/917308D9-6C92-4DA5-B4B1-B4A19451E2D2/dotnet-runtime-2.1.0-linux-x64.tar.gz
sudo mkdir /usr/share/dotnet
sudo tar xzf dotnet-runtime-2.1.0-linux-x64.tar.gz -C /usr/share/dotnet
sudo ln -s /usr/share/dotnet/dotnet /usr/bin/dotnet
```

Test the installation:

```sh
dotnet --info
```

Now, proceed with the [installation of PKI Express](linux-centos.md#install).
