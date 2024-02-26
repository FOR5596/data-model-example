# Data structure of a calibration experiment
This data model describes the structure of a calibration experiment for an analyte. The calibration experiment consists of a list of samples that were measured. Each sample contains the initial concentration and the measured signal. The calibration experiment also contains information on the measurement conditions such as the temperature and pH at which the calibration experiment was performed.

## Objects

### Calibration
A `Calibration` contains information on the measurement conditions and the actual measurements of the calibration experiment for an analyte.

- analyte_name
    - type: string
    - description: Name of the analyte that was calibrated
- __inchi__
    - type: string
    - description: InChI of the analyte that was calibrated
- __date_measured__
    - type: datetime
    - description: Timestamp of when the calibration experiment was performed
- __temperature__
    - type: float
    - description: Temperature at which the calibration experiment was performed
- __temperature_unit__
    - type: Unit
    - description: Unit of temperature
- __ph__
    - type: float
    - description: pH at which the calibration experiment was performed
- __samples__
    - type: Sample
    - multiple: True
    - description: List of samples that were used for the calibration experiment
- slope
    - type: float
    - description: Slope of the calibration curve, representing the proportionality coefficient between the concentration and the signal

### Sample
A `Sample` contains describes individual measurements of a `Calibration`. 

- __init_conc__
    - type: float
    - description: Initial concentration of the sample
- __conc_unit__
    - type: Unit
    - description: Unit of concentration
- __measured_signal__
    - type: float
    - description: Signal that was measured for the sample
- signal_unit
    - type: Unit
    - description: Unit of the signal