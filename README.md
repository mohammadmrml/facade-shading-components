# facade-shading-components
Parametric dynamic shading panels — circular, triangular, hexagonal — generated in Grasshopper, used as the geometry basis for the ML-driven facade performance predictor.

# Dynamic Shading Facade Components

Three parametric shading panel components built in Grasshopper, used to generate the dynamic shading facade (DSF) geometries evaluated in this thesis. Each component takes a base surface and produces a panelized shading Brep. These same parameter ranges were used to generate the training dataset for the Random Forest daylighting surrogate model used in the Rhino plugin (see [facade-ml-plugin](#) repo).

## Requirements
- Rhino 7 or 8
- Grasshopper (bundled with Rhino — no separate install)

## How to Run
1. Open Rhino, launch Grasshopper (`Grasshopper` command)
2. Open the desired `.gh` file (`File > Open`)
3. Bake or reference a wall/window surface into the **Srf** input — the component needs a base Brep to panelize
4. Adjust the numeric sliders/inputs described below and the panel geometry updates live

## Components

### Circular Panel
| Input | Type | Example | Description |
|---|---|---|---|
| Srf | Brep | — | Base surface to panelize |
| Radius | Number | 20 | Panel radius (cm) |
| Vertical rotation angle | Angle | — | Vertical tilt of each panel |
| Horizontal rotation angle | Angle | 20 | Horizontal tilt of each panel |
| B | Number | 0.1 | Porosity / gap factor between panels |

Output: **Panel** (Brep)

### Triangular Panel
| Input | Type | Example | Description |
|---|---|---|---|
| Srf | Brep | — | Base surface to panelize |
| Edge length | Number | 40 | Triangle edge length (cm) |
| Angle | Cluster Input | -60 | Panel rotation angle |

Output: **Panels** (Brep)

### Hexagonal Panel
| Input | Type | Example | Description |
|---|---|---|---|
| Srf | Brep | — | Base surface to panelize |
| Radius (A) | Number | 20 | Hexagon radius (cm) |
| Gap/Panel size | Number | 0.5 | Porosity / spacing between panels |
| Vertical rotation angle | Angle | — | Vertical tilt of each panel |
| Horizontal rotation angle | Angle | -40 | Horizontal tilt of each panel |

Output: **Panel** (Brep)

## License
MIT
