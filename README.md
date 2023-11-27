# io.github.GoldenGnu.jEveAssets
Asset manager for EVE Online as a Flatpak.

[https://github.com/GoldenGnu/jEveAssets](https://github.com/GoldenGnu/jEveAssets)

## How to install jEveAssets as a flatpak locally

These commands will build and install jEveAssets as a flatpak locally for your user:
```bash
git clone -b io.github.GoldenGnu.jEveAssets https://github.com/Nathan-LS/flathub.git io.github.GoldenGnu.jEveAssets
cd io.github.GoldenGnu.jEveAssets
flatpak install --user flathub org.freedesktop.Platform//23.08 org.freedesktop.Sdk//23.08
flatpak-builder --install --user --sandbox --force-clean build-dir io.github.GoldenGnu.jEveAssets.yml
```

## How to update jEveAssets locally
To update your locally built flatpak version of jEveAssets run the following commands:
```bash
cd io.github.GoldenGnu.jEveAssets
git pull
flatpak-builder --install --user --sandbox --force-clean build-dir io.github.GoldenGnu.jEveAssets.yml
```

## How to run jEveAssets
```bash
flatpak run io.github.GoldenGnu.jEveAssets
```

## How to uninstall jEveAssets
```bash
flatpak uninstall --user io.github.GoldenGnu.jEveAssets
```


## Migrating existing data into the flatpak
If you have an existing installation of jEveAssets on your system you can migrate to the Flatpak application with the following command:
```bash
rsync --delete -Pacv ~/.jeveassets/ ~/.var/app/io.github.GoldenGnu.jEveAssets/.jeveassets/
```

## Importing and exporting data from the flatpak
This flatpak has no home directory access unless additional permissions are given with a tool such as [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal).

The directory at `~/.var/app/io.github.GoldenGnu.jEveAssets/jEveAssets_mnt/` on the host is mapped to `~/.jEveAssets_mnt/` inside the Flatpak application. 
Use this folder for importing/exporting filters and exporting data.