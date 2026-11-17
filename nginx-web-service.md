# NGINX — Custom archive web page

**Status:** Reported working end to end.

## Known results

NGINX was active and listening on TCP 80. Windows initially reached the welcome page through VirtualBox NAT forwarding. Later, a host HTTP test returned 200 and the custom HTML; refreshing the browser loaded the custom page.

Recorded forwarding: `127.0.0.1:8080` on Windows to guest port 80. Recorded content path: `/var/www/black-history-archive/index.html`. Compare these with the live VM before treating them as a configuration export.

## Diagnostic commands

```bash
systemctl status nginx --no-pager
sudo nginx -t
sudo ss -lntp
curl -i http://127.0.0.1/
sudo tail -n 30 /var/log/nginx/access.log
sudo tail -n 30 /var/log/nginx/error.log
```

On Windows, use `curl.exe -i http://127.0.0.1:8080/` to explicitly select the curl executable.

NGINX `root` and `index` are configuration directives, not Bash commands. An earlier attempt to execute directives as commands led to an unintended `root-framework` installation. Cleanup was suggested, but completion is not confirmed. Inspect installed packages before removing anything.

See [INC-001](../incidents/INC-001-nginx-content.md) and the [example configuration](../configs/README.md).

**IT connection:** application support, HTTP testing, configuration validation, and log correlation.
