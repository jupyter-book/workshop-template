---
numbering:
  title:
    offset: 0
  start: 6
---
# Build using GH workflow 🌶

```{warning}
Not sure whether this is the correct title and content... at some stage people want to go do stuff locally, this would be a good place to explain how to do that.
```


## Replace date by last commit to main

```yml
    - name: Add current date to myst.yml
    shell: bash
    run: |
        BUILD_DATE="$(date +'%Y-%m-%d')"
        sed -i "s|\${BUILD_DATE}|${BUILD_DATE}|g" myst.yml
        echo "myst.yml:"
        grep -nE '^\s*date:' myst.yml
```

date:  ${BUILD_DATE} 