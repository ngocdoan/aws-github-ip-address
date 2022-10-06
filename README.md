# aws-github-ip-address
### install jq, yq, sed, wget
#### AWS

##### Document
```
https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html
```
##### Download json file
```
wget https://ip-ranges.amazonaws.com/ip-ranges.json
```
##### Get the ip range
```
cat ip-ranges.json| grep "ip_prefix" | sed 's/^.*: //' | sed 's/"//' | sed 's/",//'
```
#### Github

##### Download json file
```
wget -O github.json https://api.github.com/meta
```
##### Get the ip range
```
jq -r .hooks github.json | jq -r ".[]" >> github.txt
jq -r .web github.json | jq -r ".[]" >> github.txt
jq -r .api github.json | jq -r ".[]" >> github.txt
jq -r .git github.json | jq -r ".[]" >> github.txt
jq -r .packages github.json | jq -r ".[]" >> github.txt
jq -r .pages github.json | jq -r ".[]" >> github.txt
jq -r .importer github.json | jq -r ".[]" >> github.txt
jq -r .actions github.json | jq -r ".[]" >> github.txt
jq -r .dependabot github.json | jq -r ".[]" >> github.txt
```
