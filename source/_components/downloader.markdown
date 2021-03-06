---
layout: page
title: "Downloader"
description: "Instructions how to setup the downloader component with Home Assistant."
date: 2015-01-24 14:39
sidebar: true
comments: false
sharing: true
footer: true
logo: home-assistant.png
ha_category: Other
ha_release: pre 0.7
---

The `downloader` component provides a service to download files. It will raise an error and not continue to set itself up when the download directory does not exist.

To enable it, add the following lines to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
downloader:
  download_dir: downloads
```

Configuration variables:

- **download_dir** (*Required*): If the path is not absolute, it's assumed to be relative to the Home Assistant configuration directory (eg. `.homeassistant/downloads`).

### {% linkable_title Use the service %}

Go the the "Developer Tools", then to "Call Service", and choose `downloader/download_file` from the list of available services. Fill the "Service Data" field as shown in the example below and hit "CALL SERVICE".

```json
{"url":"http://domain.tld/path/to/file"}
```

This will download the file from the given URL.

| Service data attribute | Optional | Description |
| ---------------------- | -------- | ----------- |
| `url`                  |       no | The url of the file to download.

