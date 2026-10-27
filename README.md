# SEDSForge Pro (v1.0.0)

### CCSDS 876.0-B-1 & ISO 20652 Spacecraft Electronic Data Sheets (SEDS) Studio

SEDSForge Pro is an aerospace-grade developer studio, avionics device schema synthesizer, polynomial calibration curve evaluator, NASA Core Flight System (cFS) C header generator, and 10-point normative compliance auditor designed for spacecraft avionics systems engineers (NASA GSFC/JPL, ESA ESTEC, JAXA, MBRSC UAE), payload instrument vendors (Star Trackers, Reaction Wheels, IMUs, Magnetometers), and commercial NewSpace satellite bus developers.

---

## 🌟 Key Capabilities

- **Normative SEDS XML Synthesis (CCSDS 876.0-B-1)**: Formats schema-compliant SEDS documents (`<DataSheet>`, `<Device>`, `<Component>`, `<DeclaredTypeSet>`, `<ParameterSet>`, `<CommandSet>`, `<StateMachineSet>`).  
- **Avionics Hardware Device Archetypes**: Built-in model templates for autonomous Star Trackers (ST-200), high-torque Reaction Wheels (RW-50), and 6-DOF Fiber Optic Gyro IMUs.  
- **Polynomial & Piecewise Calibration Curves**: Evaluates multi-term polynomial calibration formulas (\$y \= \\sum c\_i x^{e\_i}\$) converting raw sensor ADC counts into physical calibrated engineering units (\$^\\circ\\text{C}\$, \$\\text{RPM}\$, \$\\text{deg/s}\$).  
- **NASA Core Flight System (cFS) C Header Synthesis**: Automatically exports flight-software-ready C header structures (`.h`) with byte-exact `OS_PACK` telemetry and telecommand memory alignments for the cFS Software Bus (CFE\_SB).  
- **Command Argument Constraint Validation**: Enforces `minInclusive` and `maxInclusive` range boundary checks for telecommand parameters.  
- **10-Point Normative Compliance Auditor**: Automated verification engine enforcing rules `SEDS-001` through `SEDS-010`.

---

## 📂 Project Structure

seds-forge-pro/

├── source-code/

│   ├── seds-engine.js           \# Core SEDS XML modeler, calibration & cFS header engine

│   ├── seds-auditor.js          \# 10-point normative compliance auditor

│   ├── seds\_cli.py              \# Pure Python 3 CLI executable

│   ├── seds-cli.py              \# Pure Python 3 CLI alias

│   ├── test\_runner.py          \# 10-suite unit test runner

│   └── index.html               \# Interactive Mission Control operations console

├── build/

│   └── seds-forge-pro-v1.0.0.zip \# Standalone production bundle

├── documentation/

│   ├── CCSDS\_SEDS\_SPECIFICATION.md \# Normative protocol specification

│   └── SEDS\_COMPLIANCE\_MATRIX.md   \# 10-point requirement traceability

└── screenshots/

    ├── architecture-diagram.svg  \# System architecture diagram

    └── seds-studio-preview.svg    \# Operations console preview

---

## 🚀 Quick Start

### Running Automated Tests

python3 source-code/test\_runner.py \-v

### Command Line Interface

\# Generate SEDS XML for Star Tracker component

python3 source-code/seds\_cli.py \--mode generate \--device star\_tracker

\# Generate SEDS XML for Reaction Wheel actuator

python3 source-code/seds\_cli.py \--mode generate \--device reaction\_wheel

\# Evaluate polynomial calibration curve (e.g. 6500 counts \-\> \+25.0 degC)

python3 source-code/seds\_cli.py \--mode calibrate \--raw 6500

\# Export NASA Core Flight System (cFS) C header file

python3 source-code/seds\_cli.py \--mode header

\# Run 10-Point Normative Compliance Audit on SEDS model

python3 source-code/seds\_cli.py \--mode audit \--device star\_tracker

### Launching the Web Operations Console

Open `source-code/index.html` in any web browser to access the interactive Mission Control dashboard, visual device modeler, polynomial calibration curve inspector, cFS C code viewer, and 10-point compliance scorecard.