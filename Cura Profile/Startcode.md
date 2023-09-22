# Mirror

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=1 MODE=MIRROR
START_PRINT EXTRUDER={adhesion_extruder_nr} EXTRUDERS=2 EXTRUDER_TEMP={material_print_temperature_layer_0, 0} EXTRUDER1_TEMP={material_print_temperature_layer_0, 1} BED_TEMP={material_bed_temperature_layer_0} AREA_START=%MINX%,%MINY% AREA_END=%MAXX%,%MAXY%

# Dual

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=0 MODE=PRIMARY
START_PRINT EXTRUDER={adhesion_extruder_nr} EXTRUDERS=2 EXTRUDER_TEMP={material_print_temperature_layer_0, 0} EXTRUDER1_TEMP={material_print_temperature_layer_0, 1} BED_TEMP={material_bed_temperature_layer_0} AREA_START=%MINX%,%MINY% AREA_END=%MAXX%,%MAXY%

# Copy

M190 S0
M109 S0
G28 X
SET_DUAL_CARRIAGE CARRIAGE=1 MODE=COPY
START_PRINT EXTRUDER={adhesion_extruder_nr} EXTRUDERS=2 EXTRUDER_TEMP={material_print_temperature_layer_0, 0} EXTRUDER1_TEMP={material_print_temperature_layer_0, 1} BED_TEMP={material_bed_temperature_layer_0} AREA_START=%MINX%,%MINY% AREA_END=%MAXX%,%MAXY%