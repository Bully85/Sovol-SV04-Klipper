# Mirror

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=1 MODE=MIRROR
START_PRINT EXTRUDER=[current_extruder] EXTRUDERS=2 EXTRUDER_TEMP={first_layer_temperature[0]} EXTRUDER1_TEMP={first_layer_temperature[1]} BED_TEMP={first_layer_bed_temperature[0]}

# Dual

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=0 MODE=PRIMARY
START_PRINT EXTRUDER=[current_extruder] EXTRUDERS=2 EXTRUDER_TEMP={first_layer_temperature[0]} EXTRUDER1_TEMP={first_layer_temperature[1]} BED_TEMP={first_layer_bed_temperature[0]}

# Copy

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=1 MODE=COPY
START_PRINT EXTRUDER=[current_extruder] EXTRUDERS=2 EXTRUDER_TEMP={first_layer_temperature[0]} EXTRUDER1_TEMP={first_layer_temperature[1]} BED_TEMP={first_layer_bed_temperature[0]}