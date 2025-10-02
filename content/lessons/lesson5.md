# Build using GH workflow


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