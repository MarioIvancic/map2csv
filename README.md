# map2csv
Converts GCC MAP file to XSLS (Excel) format.

Currently, script is configured to ignore some sections commonly found on ARM CPUs/MCUs.

# Usage
```
map2csv [-o output-file.xlsx] [input-file.map]
```
Default output file is output.xlsx. Default input file is stdin.

# Examples
```
map2csv input.map
cat input.map | map2csv
map2csv -o output.xlsx input.map
map2csv -ooutput.xlsx input.map
cat input.map | map2csv -o output.xlsx
```

# Install
Copy this file to /usr/local/bin or ~/.local/bin


# Dependencies
This script uses Excel::Writer::XLSX perl library. You can install it from OS package manager or using cpan.
```
cpan -i Excel::Writer::XLSX
```


# Todo
Add command line switch to set sections names that should be ignored.
