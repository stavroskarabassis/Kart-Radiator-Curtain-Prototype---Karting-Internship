# Kart-Radiator-Curtain-Prototype---Karting-Internship
Parametric FreeCAD (Python) generators for adjustable radiator curtains used
in competition karting. Each script builds a 3D model and exports to STEP,
with all key dimensions exposed as parameters at the top of the file.

A radiator curtain regulates how much air reaches the radiator, keeping the
engine within its target temperature window — mainly to prevent overcooling
in cold or variable conditions. These designs explore different mechanisms
for doing that reliably.

## Designs

| Script | Mechanism | Notes |
|--------|-----------|-------|
| `zonal` | Graduated zonal sheet | Edges covered first, centre last (aero-optimal) |
| `louvre` | Pivoting slats + tie-rod | Continuous adjustment via one lever |
| `iris` | Fixed edge panels + central diaphragm | Fine control where flow matters most |
| `aeroelastic` | Flexi-blades that bend with airspeed | Passive, self-regulating (cantilever model) |
| `double-deck` | Recovery holes + guide channels | Redirects stagnation-zone air to the hot upper core |
| `railed-zonal` | Zonal panels on a sliding curtain rail | Window-curtain analogy, hybrid design |

## Requirements

- [FreeCAD](https://www.freecad.org/) 0.21+ (or 1.x)

## Usage

Headless:
```bash
freecadcmd <script>.py
```

Or inside the FreeCAD GUI Python console:
```python
exec(open(r'/path/to/<script>.py', encoding='utf-8').read())
```

Output: a `.step` file in the working directory. Edit the parameters block
at the top of each script before running to match your own radiator.

## Design approach

Each design works backward from a target: keep the engine at its optimal
temperature with maximum reliability under real dynamic-pressure and
vibration loads. Several scripts also print calibration figures (e.g.
blade deflection vs. speed, mesh blockage %) to help tune parameters.

## Disclaimer

These are engineering-exploration models, not validated race parts. Any
non-standard component should be checked against your championship's technical
regulations and confirmed with a scrutineer before use.

## License

[MIT](LICENSE)
