### OIDC connect create 

eksctl utils associate-iam-oidc-provider --cluster roboshop-dev --approve 

### Create service account 

eksctl create iamserviceaccount --cluster roboshop-dev --name secret-reader --namespace roboshop --attach-policy-arn arn:aws:iam::445567085619:policy/Roboshop-mysql-secret-Reading --approve

### Get secret value 

aws secretsmanager get-secret-value --secret-id roboshop/dev/mysql_password --query SecretString --output text



