# Timing libs, hierarchical vs flat synthesis and Efficient flop coding styles

### Introduction to Timing Libraries
- Timing libraries (.lib files) are critical for digital design because they:
- Contain timing, power, and area details for each standard cell.
- Guide synthesis tools for accurate logic mapping and analysis.
- Model how gates and flip-flops behave under different PVT (Process, Voltage, Temperature) conditions.

### 🌡 What is PVT?
PVT defines the three main factors that influence IC behavior and timing:
- Process (P): Variations in manufacturing can make transistors faster (ff), slower (ss), or typical (tt).
- Voltage (V): Supply voltage of the chip.
    - Higher voltage → faster switching, but more power consumed.
    - Lower voltage → slower switching, but lower power use.
- Temperature (T): Impacts transistor performance.
    - Higher temperature → slower switching (resistance increases).
