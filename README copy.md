Get All objects

sam package --s3-bucket plm-hands-on-dynamodb-lab --output-template-file packaged.yaml
sam deploy --template-file packaged.yaml --stack-name user-mgt-app-hands-on --capabilities CAPABILITY_IAM

```
aws dynamodb scan --table-name UsersTable

aws dynamodb scan \
     --table-name UsersTable \
     --filter-expression "last_login = : last_login" \
     --expression-attribute-values '{": last_login”:{“N”:1546519879010}}'

aws dynamodb scan \
     --table-name UsersTable \
     --filter-expression "last_login = :last_login" \
     --expression-attribute-values '{":last_login":{"N":"1546519879010"}}'
```
