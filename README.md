# aws-github-ip-address
### install jq, yq, sed, wget
#### AWS

##### Document
```
https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html
```
```
wget https://ip-ranges.amazonaws.com/ip-ranges.json
```
```
cat ip-ranges.json| grep "ip_prefix" | sed 's/^.*: //' | sed 's/"//' | sed 's/",//'
```
