# Compact Line Address Format
Simple mapping from source lines to addresses. 

## On-disk format

### Header
```C
uint16_t magic 0xC1AF
uint8_t version
uint8_t memory_model
uint32_t flags
uint32_t comp_unit_sect_offset
uint32_t line_addr_sect_offset
uint32_t string_table_offset
uint32_t string_table_length
```

### Compilation Unit Section
```C
uint32_t comp_unit_id
uint32_t comp_unit_name_idx
uint32_t comp_unit_id
uint32_t comp_unit_name_idx
uint32_t comp_unit_id
.
.
.
```

### Line Section
```C
uint32_t comp_unit_id
uint32_t line_no
uint32_t/uint64_t address
uint32_t comp_unit_id
uint32_t line_no
.
.
.
```

### String Table 
NULL-separated list of strings.

## Author
Daniel Lovasko lovasko@freebsd.org
