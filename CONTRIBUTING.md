# Contributing

Contributions to the library are welcome!

## Issues, Feedback, and Feature Requests

Creating issues, feedback, and feature requests should follow the standard submission process through the GitHub [Issues](../../issues) section of the repository.

## Pull Requests

Creating pull requests should follow the standard submission process through the GitHub [Pull requests](../../pulls) section of the repository.

## Library Packing

Each symbol library is stored [unpacked](https://gitlab.com/kicad/libraries/kicad-symbols/#kicad-symbols) as a `.kicad_symdir` directory, each
containing multiple symbol files ending in `.kicad_sym`.

## Vacuum Tube Design Standards

You may review existing library symbols for examples of the following.

### Symbol Attributes

- Name and Value: Manufacturer's model number
- Reference: V
- Footprint: Leave blank
- Datasheet: URL of the manufacturer's PDF datasheet
- Description: Source from the **RCA Receiving Tube Manual** or manufacturer's datasheet
  - Examples: Full-Wave Vacuum Rectifier, Beam Power Tube, Power Pentode, High-μ Twin Triode
- Base (custom field): Source from the **RCA Receiving Tube Manual** or manufacturer's datasheet
  - Examples: Octal 7AC, Noval 9A
- Keywords: Space-separated list of alternate names and equivalent tubes
  - Do not include suitable replacement tubes!

### Units and Body Styles

- Beam Tetrodes shall include two named units
  - Unit A name: Beam Tetrode
  - Unit B name: Filament
- Power Pentodes shall include two named units
  - Unit A name: Power Pentode
  - Unit B name: Filament
- Triodes shall include three named units
  - Unit A name: Triode A
  - Unit B name: Triode B
  - Unit C name: Filament
- Triodes shall include two custom body styles
  - Body Style A name: Full Envelope
  - Body Style B name: Partial Envelope
- "All units are interchangeable" should be disabled for multi-unit symbols

### Elements, Line Widths, and Line Styles

- Envelopes shall be circles with a **400 mil** radius and a **10 mil** line width
- The line style of the *right* half of Triode envelopes shall be **Dashed**
- Anodes shall be rectangles with a **40 mil** height, **5 mil** corner radius, **1 mil** line width, and **solid** fill
- Cathodes shall match anode characteristics but shall also include "legs"
- Cathode legs shall be rectangles with a **20 mil** height, **5 mil** corner radius, **1 mil** line width, and **solid** fill
- Grids shall be lines with a **21 mil** line width
- Filaments shall be arcs with a **90°** angle
- Lines connecting pins to anodes, cathodes, and filaments shall be in contact with those elements
- Lines connecting pins to grids shall be spaced **25 mils** away from those elements
- Rectifier exceptions
  - Anodes shall be lines with a **41 mil** line width
  - Cathodes shall be arcs with a **41 mil** line width and a **90°** angle

### Pin Attributes

- Pin names shall be hidden
- Pin names shall be uppercase
- Pin names and pin numbers shall match those found in the manufacturer's data sheet
  - Including the use of the prime symbol (`′` or Unicode U+2032)
  - Subscripts shall be converted to simple uppercase characters or numerals
- Multi-use pin names shall have their identifiers separated by a comma (no spaces)
  - Examples: Filament + Cathode = "F,K"
  - Note: Filament (F) should always come first
- The electrical type of pins shall be **Passive**

### Field Placement

- Reference: `(500, -500)` (Autoplacement **disabled**)
- Value: `(500, -400)` (Autoplacement **disabled**)
- Description: `(0, 1000)`
- Base: `(0, 1100)` (Show field name **enabled**)
- Datasheet: `(0, 1200)`

### Source Material

- **[RCA Receiving Tube Manual, Issue RC‑30 (1975)](https://archive.org/download/RCA_RC-30_1975/RCA%20RC-30%201975_text.pdf)**
