csvファイルのカラム数をカウント

```bash
cat sample.csv | awk -F ',' '{print NF}'
```
