# Qyvaria

**Qyvaria** is the public home of **Qyvaria OS**, the **Qyvaria Python kernel**,
Qyvaria Studio website materials, and related project documentation.

Owner: **John Havlasek**  
Contact: **Qyvaria1ai@gmail.com**

## Licence

The Qyvaria source code, including the Qyvaria kernel released in this repository,
is licensed under the:

# Apache License 2.0

SPDX identifier: `Apache-2.0`

This means people may:

- use Qyvaria commercially;
- study and reverse engineer the source;
- modify it;
- fork it;
- redistribute it;
- combine it with other software;
- build commercial products with it;

subject to the Apache-2.0 requirements, including preservation of licence and
NOTICE information where applicable.

See:
- `LICENSE`
- `NOTICE`

## Project scope

This repository is intended to contain:

- the Qyvaria Python kernel;
- Qyvaria OS source and related code;
- public website HTML and documentation;
- public release metadata;
- third-party licence notices;
- contribution and security policies.

## Official downloads

Public source repository:
- `https://github.com/Havlasek1John/Qyvaria`

Qyvaria OS release/download repository:
- `https://github.com/Havlasek1John/Qyvaria-OS-`

## Repository structure

```text
Qyvaria/
├─ README.md
├─ LICENSE
├─ NOTICE
├─ CONTRIBUTING.md
├─ SECURITY.md
├─ CODE_OF_CONDUCT.md
├─ TRADEMARKS.md
├─ THIRD_PARTY_NOTICES_DRAFT.md
├─ docs/
│  ├─ FULL_APACHE_LICENSING_PLAN.md
│  ├─ GITHUB_AND_SITE_CHANGES.md
│  ├─ OUTPUT_POLICY.md
│  ├─ PRIVACY_POLICY_DRAFT.md
│  ├─ WEBSITE_TERMS_DRAFT.md
│  └─ RELEASE_CHECKLIST.md
├─ site/
│  └─ qyvaria_full_apache_site.html
├─ public/
│  └─ README.md
└─ releases/
   └─ README.md
```

## Credit

Suggested credit where practical:

> Qyvaria by John Havlasek.

or

> Built with Qyvaria.

Apache-2.0 does not require every product UI to show a marketing credit, but it
does preserve copyright and NOTICE obligations where applicable.

## Third-party software

Qyvaria uses or may integrate with open-source packages, APIs, models, and tools.
Those third-party materials keep their own licences and terms.

A draft inventory is included in:
- `THIRD_PARTY_NOTICES_DRAFT.md`

Before final public release, generate a versioned dependency list and SBOM from
the actual build environment.

## Security reports

Send security reports to:
- `Qyvaria1ai@gmail.com`

## Cloudinary/media note

Frontend website files should contain only public delivery URLs and public-safe
asset identifiers. Never place Cloudinary API secrets or other secrets in HTML,
JavaScript, README files, or GitHub commits.

## Included Qyvaria OS public software release

This repository upload package also includes the Qyvaria OS public Windows release
artifacts under:

- `releases/QyvariaOS_GitHub_Public_Release_Package/`

That folder contains:
- the Windows installer executable;
- the installer ZIP wrapper;
- public icon assets;
- release notes;
- SHA-256 checksums;
- a release manifest.

The standalone Qyvaria kernel source remains at:
- `qyvaria.py`

