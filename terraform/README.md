# Teleport Terraform 

Teleportの構成をAWS環境上で作成するためのTerraformサンプルとなる。
AWS上での必要リソース(EC2/S3など)を構成を作成するのみのTerraformとなり、Teleport自体のセットアップは行わない。

- Main
Auth/Proxy/Bastion/Nodeとして役割を分割し最大構成で作成する

- Slave
1台のEC2に機能を集約し、最小構成で作成する

# 構成図
![Sample](https://github.com/cloudnative-co/teleport_renovation/blob/fa69a337471bf61c384e6c826de96ad6e9202580/Picture/Terraform_Sample.png "サンプル")

# 実行手順

##  環境変数を設定
```
# 公開鍵を登録
export TF_VAR_public_key=""
# Route53に登録済みのドメインを使用
export TF_VAR_domain="teleport.example.com"
# 設定済みのProfile名を使用
export AWS_PROFILE="saml"
# リージョンを指定
export AWS_DEFAULT_REGION="ap-northeast-1"
```

## Terraform実行
```
# Init
terraform init
# Plan
terraform plan
# Apply
terraform apply
```
