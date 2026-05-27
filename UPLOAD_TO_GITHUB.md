# Upload to GitHub

Repository:

```text
https://github.com/Havlasek1John/Qyvaria
```

## Best simple upload

Use the flat web-upload ZIP if GitHub gives upload errors with folders.

1. Unzip the package on your computer.
2. Open the GitHub repository.
3. Click **Add file**.
4. Click **Upload files**.
5. Drag the files from inside the unzipped folder.
6. Do **not** upload the ZIP itself.
7. Commit with:

```text
Set up public Qyvaria GitHub repository
```

## Upload large OS packages

Upload the large OS package ZIP files through **Releases**, not the normal repository file list.

Suggested release name:

```text
Qyvaria OS 1.0.63.6 Public Release
```

Suggested release assets:

```text
Qyvaria_OS_Windows.zip
Qyvaria_OS_Linux.zip
qyvaria.py
```

## If upload fails again

Upload in two stages:

1. First upload all `.md`, `LICENSE`, `NOTICE`, `CITATION.cff`, `pyproject.toml`, and `requirements.txt`.
2. Commit.
3. Then upload `qyvaria.py` alone.
4. Commit.
