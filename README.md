# RDM Flatpak files

Needed files for the packaging of [RDM](https://github.com/uglide/RedisDesktopManager) in Flatpak.

# Upload to Flathub

Check this Flathub's [tutorial](https://github.com/flathub/flathub/wiki/App-Submission#how-to-submit-an-app)

# Update Python deps

```
wget https://raw.githubusercontent.com/flatpak/flatpak-builder-tools/master/pip/flatpak-pip-generator
chmod +x flatpak-pip-generator
rm pip-dependencies.json
./flatpak-pip-generator --requirements-file=/RDM/src/py/requirements.txt --output pip-dependencies
```

# Build & Test
```
flatpak-builder build dev.rdm.RDM.json --force-clean
flatpak-builder --user --install build dev.rdm.RDM.yml
flatpak run dev.rdm.RDM
```

# Errors

For an unknown reason, the styles on the app are a bit buggy.
Since I don't know that much about Qt nor Flatpak, I have asked the Flatpak KDE runtime developers for help.

See https://invent.kde.org/packaging/flatpak-kde-runtime/-/issues/20

Also, since my use of the app is quite simple (just locally) I haven't fully tested it.
