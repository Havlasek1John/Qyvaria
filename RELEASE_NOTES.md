# Qyvaria OS 1.0.63.6 Public Release Notes

## Summary

This release publishes public Qyvaria OS package assets and the Qyvaria `qyvaria.py` Python kernel bundle.

## Release assets

| Asset | Purpose | SHA-256 |
|---|---|---|
| `Qyvaria_OS_Windows.zip` | Windows desktop package | `519233fbaad9bb29e424d7c7983365afff90b2befda8a8ef9025b569dc4502da` |
| `Qyvaria_OS_Linux.zip` | Linux desktop package | `1c615659dec5463a67e8acf561a1460cfc083fa97ff1f8ca3baf1bafecc3551e` |
| `qyvaria.py` | Single-file Python kernel bundle | `8fbe528dfe604d6cdc7223caae364dca8c029b3e317dd3d8721f0dab0d027ad8` |

## Recommended installation

### Windows

```bat
unzip Qyvaria_OS_Windows.zip
SETUP_QYVARIA_OS_WINDOWS.cmd
```

### Linux

```bash
unzip Qyvaria_OS_Linux.zip
chmod +x SETUP_QYVARIA_OS_LINUX.sh
./SETUP_QYVARIA_OS_LINUX.sh
```

## Notes

- Qyvaria OS desktop packages may restore Electron/npm dependencies on first run.
- Internet access may be required for first setup.
- Review all package contents before running scripts on a production machine.
