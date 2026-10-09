# Digital Twin Authoring Platform (Unity 2021.3 LTS)

> **Digital Twin Authoring Platform** is a research project aimed at streamlining the creation and exploitation of Digital Twins (DTs) of archaeological sites and artifacts, for both **research** and **dissemination**.
> The platform provides
>
> - a no-code authoring environment integrating 3D reconstructions of sites and artifacts with semantic information (points of interest, annotations, multimedia)
> - a client-server content management system, with import/export of data in the **CIDOC CRM** standard
> - desktop and **Virtual Reality** interfaces to explore the resulting case studies
>
> To dig more into the details about the platform design, you can refer to the paper (see [**Citation**](#citation))

## Table of contents

- [Introduction](#introduction)
- [Builds](#builds)
- [Source code](#source-code)
- [Configuration](#configuration)
- [Supported formats](#supported-formats)
- [Third-party software](#third-party-software)
- [Forking Policies](#forking-policies)
- [Citation](#citation)
- [Contact](#contact)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Introduction

Most Cultural Heritage digitisation projects result in ad hoc, single-site applications that are rarely reusable. This platform allows users with limited technical expertise to register a site, populate it with artifacts, points of interest (POIs) and annotations, and organize them in **case studies**, which can be edited, shared and explored.

The application offers two operation modes:

- **Research Mode** (desktop): create sites, add contents and resources, build case studies, place artifacts (translation/rotation widgets, snapping, physics-based placement), annotate locations and artifacts, import/export CIDOC CRM data.
- **Dissemination Mode** (desktop and tethered VR): explore the prepared case studies by teleporting between POIs, selecting contents via raycasting to open information panels (images, videos, audio, text), and grabbing, rotating and scaling artifacts.

Data are stored in an SQLite database, kept on each client and synchronized with a server. Offline operation is not supported.

## Builds

The latest version of the executable (`DTAuthoring.exe`) is already available for download in [**Release**](../../releases). *(TODO: link)*

The application targets **Windows** and VR systems compatible with Unity XR. It has been tested with the **Meta Quest 2** (tethered) with its controllers, on a workstation with an NVIDIA GTX 970 (desktop) and GTX 1080 (VR). Standalone (untethered) execution is not supported.

## Source code

This repository contains the **source code (C# scripts) only**. The Unity project (scenes, prefabs, UI assets and project settings) is **not** included, so the repository cannot be opened and built directly as a Unity project. The executable available in [**Release**](../../releases) is the reference build.

The code was developed and tested with **Unity 2021.3 (LTS)**. To explore or reuse it:

1. Create a new Unity 2021.3 (LTS) project.
2. Copy the contents of the Scripts folder into the `Assets/` folder of the project.
3. Import the [third-party software](#third-party-software) that is not included in the repository.

## Configuration

The server address and the other settings are read from a local configuration file. *(TODO: file name, location and example content.)*

## Supported formats

| Resource          | Formats                                          |
|---                |---                                               |
| 3D models         | `.gltf`, `.fbx` (no animations), `.obj` + `.mtl` |
| Textures / images | `.jpg`, `.png`                                   |
| Video             | `.mp4`, `.mkv`                                   |
| Audio             | `.mp3`, `.wav`                                   |

## Third-party software

The following third-party software is used by the code and is **not** included in the repository. Each component must be obtained separately, under its own license.

| Software                         | Purpose                      |
|---                               |---                           |
| Unity 2021.3 LTS                 | Engine                       |
| Unity XR Interaction Toolkit     | VR interaction               |
| [glTF importer]                  | Runtime `.gltf` import       |
| [FBX importer]                   | Runtime `.fbx` import        |
| Runtime OBJ Importer             | Runtime `.obj`/`.mtl` import |
| [Cesium]                         | 3D virtual globe             |
| [Other: fonts, icons, UI assets] | UI                           |

## Forking Policies

Please contact [Federico De Lorenzis](mailto:federico.delorenzis@polito.it) **BEFORE** forking the project.

## Citation

Please cite this paper in your publications if it helps your research.

```
@article{dtauthoring,
  author = {De Lorenzis, Federico and Valente, Lorenzo and Pachera, Giovanni and Spallone, Roberta and Lamberti, Fabrizio and Rossi, Corinna and Ferraris, Enrico and Del Vesco, Paolo and Taverni, Federico and Greco, Christian},
  title = {Streamlining Exploitation of Digital Archaeological Sites: A Scalable Authoring Platform to Build Digital Twins of Cultural Heritage for Research and Dissemination},
  journal = {ACM Journal on Computing and Cultural Heritage},
  year = {2026},
  doi = {TODO}
}
```

The platform design is detailed in:

- *Streamlining Exploitation of Digital Archaeological Sites: A Scalable Authoring Platform to Build Digital Twins of Cultural Heritage for Research and Dissemination*
  * [**ACM JOCCH**](TODO: DOI link)

## Contact

Maintained by [Federico De Lorenzis](mailto:federico.delorenzis@polito.it) - feel free to contact me!

## License

The source code is licensed under the [**Apache License 2.0**](LICENSE). The case-study dataset used in the paper is not included in this repository.

## Acknowledgements

This work has been carried out within the framework of the VR@POLITO initiative, with the support of experts from the Museo Egizio in Turin.
