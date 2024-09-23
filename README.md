# Gopipe

Gopipe は、ローカルのファイルを Amazon S3 バケットにコピーするためのツールです。

- 5MB以上のファイルの場合、S3のMultipart Uploadを使用し、ファイルをチャンクに分割してアップロードします。(Bidirectional Streaming RPCを使用)
- 5MB未満のファイルの場合は、通常のアップロードを行います。(Unary RPCを使用)

```bash
# Test Command
go run main.go -file_path ~/test.txt -bucket bucket -profile your-profile-name -dest_key test.txt
```

## TODO

- gRPCサーバのKubernetesデプロイ
- gRPC通信のTLS対応