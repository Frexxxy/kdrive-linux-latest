# kDrive Latest (Linux AppImage, amd64)

Stable "latest" download URL for the [Infomaniak kDrive](https://www.infomaniak.com/en/ksuite/kdrive) Linux AppImage,
for use with Gear Lever's *Static URL* update feature.

Fork of [eylenburg/kdrive-linux-latest](https://github.com/eylenburg/kdrive-linux-latest) with a reworked workflow.

## Stable URL

https://github.com/Frexxxy/kdrive-linux-latest/releases/latest/download/kDrive-latest-amd64.AppImage

Only amd64 (x86_64) is provided.

## How to use with Gear Lever

1. Open **Gear Lever** and select your kDrive AppImage.
2. In **Update Management**, choose **Static URL**.
3. Paste the URL above and save.

## How it works

- A GitHub Action runs daily (08:00 UTC) and can be started manually (*Actions → Run workflow*).
- It reads Infomaniak's update JSON (`https://www.infomaniak.com/drive/latest`).
- Only download URLs under `https://download.storage.infomaniak.com/drive/desktopclient/` are accepted.
- The AppImage is downloaded only if the version differs from the current release title (`kDrive <version>`).
- The file is uploaded unchanged to the `latest` release; its SHA-256 is printed in the workflow log.
- No third-party actions are used, only `curl`, `jq` and the GitHub CLI preinstalled on the runner.

## Note

GitHub disables scheduled workflows after about 60 days without repository activity.
If the release title stops showing new versions, re-enable the workflow under *Actions*.
