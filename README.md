# OpenWRT | Docker | Jellyfin_tweaks

changes the appearance of the Jellyfin web interface by mounting your own files for the icon, banner, logo, and settings.

```shell
  cmd="$cmd -v /somepath/favicon.ico:/jellyfin/jellyfin-web/bc8d51405ec040305a87.ico:ro"
  cmd="$cmd -v /somepath/banner-light.png:/jellyfin/jellyfin-web/assets/img/icon-transparent.png:ro"
  cmd="$cmd -v /somepath/banner-light.png:/jellyfin/jellyfin-web/assets/img/banner-light.png:ro"
  cmd="$cmd -v /somepath/logo.png:/jellyfin/jellyfin-web/logo.png:ro"
  cmd="$cmd -v /somepath/config.json:/jellyfin/jellyfin-web/config.json:ro"
```

change the page title

```Shell
docker exec -it jellyfin sh -c "sed -i 's/document.title=\"Jellyfin\"/document.title=\"JellySomething123\"/' /jellyfin/jellyfin-web/main.jellyfin.bundle.js && sed -i 's/document.title=e||\"Jellyfin\"}/document.title=e||\"JellySomething123\"}/' /jellyfin/jellyfin-web/main.jellyfin.bundle.js && sed -i 's/<title>Jellyfin/<title>JellySomething123/' /jellyfin/jellyfin-web/index.html"
```


