
extract output from json file

```
cat output_file | jq -c '.results[] | {url:.url,status: .status}'
```