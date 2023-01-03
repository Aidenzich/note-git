# tree
<details>
  <summary><strong><em>Install</em></strong></summary>

- for linux
    ```
    sudo apt-get install tree
    ```
- for mac
    ```
    brew install tree
    ```
</details>

## Usage
```
tree .
```
### Usage with `.gitignore`
```
git ls-tree -r --name-only HEAD | tree --fromfile
```