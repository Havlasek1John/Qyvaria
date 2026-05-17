# Third-Party Notices — Draft Verification List

This is a draft inventory based on dependency families observed in the reviewed
Qyvaria bundle. It is not yet a final licence report.

## Important limitation

Imports alone do not prove:
- exact package version;
- whether a package is bundled into the installer;
- transitive dependency presence;
- model/dataset/font/media licensing;
- effective licence in a specific release.

Before final publication, generate a versioned SBOM and dependency licence report
from the actual Qyvaria build environment.

## Dependency families to verify

| Dependency family | Likely role |
|---|---|
| `numpy` | numeric processing |
| `pandas` | data workflows |
| `scikit-learn` / `sklearn` | ML utilities |
| `torch` | ML runtime |
| `transformers` | model tooling |
| `datasets` | dataset utilities |
| `fastapi` | API endpoints |
| `pydantic` | schemas/validation |
| `uvicorn` | ASGI serving |
| `cryptography` | cryptographic functions |
| `PIL` / Pillow | imaging |
| `opencv` / `cv2` | image/video processing |
| `matplotlib` | plotting |
| `networkx` | graph operations |
| `onnxruntime` | inference runtime |
| `streamlit` | UI app |
| `openai` | API client |
| `diffusers` | model pipelines |
| `llama_cpp` | local model integration |
| `faster_whisper` / `whisper` | speech tooling |
| `nacl` | signing/crypto wrapper |
| `piexif` | EXIF metadata |
| `imageio` | media processing |
| `jsonschema` | schema validation |
| `unidecode` | text normalization |

## Final release process

1. Freeze package versions.
2. Export dependency manifest.
3. Generate SBOM in SPDX or CycloneDX format.
4. Generate a licence report.
5. Include required upstream licence texts/notices.
6. Review model, dataset, font, and media licences separately.
