```base
views:
  - type: table
    name: Table
    filters:
      and:
        - file.inFolder("Content/Custom")
    order:
      - file.name
      - file.ctime
      - file.folder
    sort:
      - property: file.ctime
        direction: ASC

```
