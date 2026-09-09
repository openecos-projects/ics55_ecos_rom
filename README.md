# ICS55 ECOS ROM

Integration packages for ICS55 ROM macros.

## Package contents

Each archive contains files for one ROM configuration:

| Directory | Contents |
| --- | --- |
| `doc/` | Datasheet |
| `lef/` | Physical abstract |
| `lib/` | Liberty timing and power models for all eight corners |
| `verilog/` | Three Verilog models and an all-zero `.romcode` file |
| `power/` | CPF power intent |

## Simulate your ROM content

The included `.romcode` file starts with every bit set to zero. Replace its contents locally to simulate your program or data with the Verilog models. Use one binary word per line, in ascending address order, with the most significant bit first. Keep the file name, word count, and bits per word consistent with the selected configuration. Run simulation from the extracted instance directory so the models can read `verilog/<instance>.romcode`.

## Prepare for tapeout

For tapeout, add a note to your ECOS Factory order requesting ROM content replacement and matching layout generation. We will confirm your ROM configuration and final content before generating the layout. The content is fixed in the fabricated ROM; editing the simulation file changes the simulation only.
