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
