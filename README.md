# RevProx
Fast, streaming reverse proxy and webdav proxy written in PHP

## What is RevProx?
RevProx is an extremely fast reverse proxy written in PHP (so it's compatible with most shared hosting services).

## Why another PHP reverse proxy?
RevProx takes a different approach to reverse proxying. Instead of downloading the origin content completely and then serving the download content to the client, **RevProx serves the content to the client while the origin content is being downloaded.**

#### What does this mean?
By streaming the file content directly to the client, RevProx enables **reverse proxying of files of unlimited size**. RevProx also enables the **proxying of music/video files/streams** which would normally be impossible to proxy with conventional means.

## Usage
1. Download the script to your server: `wget "https://raw.githubusercontent.com/null-dev/RevProx/master/proxy.php"`.
2. Configure the script (open it in your text editor, instructions inside the script on configuration).
3. Rewrite all requests to the downloaded script.

## Webdav
RevProx can also be used to expose webdav servers as regular web servers. RevProx can authenticate to the webdav server on behalf of clients. RevProx will also generate a directory listing since some webdav servers will not generate one themselves.

To use RevProx-Webdav, follow the instructions in the Usage section, replacing the download command with: `wget "https://raw.githubusercontent.com/null-dev/RevProx/master/proxy-webdav.php"`.

Caveat: RevProx-Webdav will only generate directory listings if the URL ends in a slash (since it is not able to differentiate between directories and files from just the URL otherwise).
