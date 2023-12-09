# map2csv
Converts GCC MAP file to XSLS (Excel) format.

By default, script will ignore some sections commonly found on ARM CPUs/MCUs. You can override this list using -i command line option.

# Usage
```
map2csv [-o output-file.xlsx] [-i ignored-sections] [input-file.map]
```
Default output file is output.xlsx. Default input file is stdin. Default ignored sections are '.ARM.attributes, .ARM.exidx, .ARM.extab'.

# Command line options
Option -o specifies output file name. You can use it in two forms: '-ofile' or '-o' 'file'. Don't forget .xlsx extension.

Option -i specifies list of ignored sections or a file containing list of ignored sections. You can use it in two forms: '-isections' or '-i' 'sections'.

If file 'sections' exists and is readable sections will be read from that file.

In any case, sections are comma separated list of sections to be ignored. Space characters around comma characters are ignored.

In case that 'sections' contain just word 'arm', it is replaced by internal list of ignored sections for ARM cpu. That list is '.ARM.attributes, .ARM.exidx, .ARM.extab'.

Note that sections '.debug_frame, .debug_str, .debug_aranges, .debug_abbrev, .debug_info. .debug_line. .debug_loc, .comment' are always ignored.

# Examples
```
map2csv input.map
cat input.map | map2csv
map2csv -o output.xlsx input.map
map2csv -ooutput.xlsx input.map
map2csv -iarm input.map
map2csv -i arm input.map
map2csv -i.data input.map
map2csv -i ignored-sections.txt input.map
```

# Install
Copy this file to /usr/local/bin or ~/.local/bin


# Dependencies
This script uses Excel::Writer::XLSX perl library. You can install it from OS package manager or using cpan.
```
cpan -i Excel::Writer::XLSX
```


# Todo
None.
