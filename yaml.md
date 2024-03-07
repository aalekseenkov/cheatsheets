# YAML

YAML is a human-readable data serialization language.  
It is commonly used for configuration files and in applications where data is being stored or transmitted. 
## Scalar Types
```
n1: 1 # integer
n2: 1.537 # float
```
```
s1: yaml # string
s2: "yaml" # string
s3: 'yaml' # string
```
```
b: true # boolean
d: 2023-12-02 # date
```
## Sequence
```
- item_1
- item_2
- item_3
```
## Mapping
```
bo: 999999
year: 1997
```
## Sequence Mapping
```
attributes:
  - a1
  - a2
methods: [m1, m2]
```
## Comments
```
# single line
# block level
# comment 1
# comment 2
```
## Indicators
`---` - document header  
`...` - document terminator
`%` - directive  
`?` - key indicator  
`:` - value indicator  
`&` - anchor property  
`*` - alias  
`-` - nested series entry  
`|` - block scalar  
`>` - folded scalar  
`+` - keep chomp modifier  
`,` - separate in-line  
`[]` - surround in-line series  
`{}` - surround in-line keyed

## Core types
`!!map {Hash table, dictionary, mapping}`  
`!!seq {List, array, tuple, vector, sequence}`  
`!!str Unicode string`  

## Special keys
`=` - default "value" mapping key  
`<<` - merge keys from another mapping  

## Variables
Declarations of skills as an anchor
```
skills: &SKILLS
  - Bash
  - Linux
```
Referencing the anchored skills
```
developer1_skills: *SKILLS
developer2_skills: *SKILLS
```
## Multiline strings
```
company: |
  Line 1
  Line 2
```
## Folded strings
```
company: >
  Line 1
  Line 2
```
## Documents
```
---
document: This is document 1
---
document: This is document 2
```
