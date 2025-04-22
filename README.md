# AURORA

[README_EN](https://github.com/aurora-develop/aurora/blob/main/README_EN.md)

（UI付き）GPT3.5を無料で提供、3.5を使用したアクセス呼び出しをサポート

# コミュニケーショングループ
https://t.me/aurora_develop

# Web 

http://your server ip:8080/web にアクセスしてください

![web](https://jsd.cdn.zzko.cn/gh/xiaozhou26/tuph@main/images/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-04-07%20111706.png)


### 注: ログインなしで ChatGpt を使用できるのは IP ベースのロケーションのみです (Baseurl をカスタマイズして制限を回避することもできます)

## Deploy

### Glitch展開する

[![Deploy to Glitch](https://cdn.glitch.com/2703baf2-b643-4da7-ab91-7ee2a2d00b5b%2Fremix-button.svg)](https://github.com/aurora-develop/aurora-glitch)

### Vercel展開する

vercelのgoはストリーミングをサポートしていないため、vercelにデプロイする場合はSTREAM_MODEにFalseを入力してください。デフォルトのストリーミング クライアントはサポートされていませんが、没入型翻訳はサポートされています。

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Faurora-develop%2Faurora&env=STREAM_MODE&project-name=aurora&repository-name=aurora)

### Render展開する
[![Deploy](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

### Koyeb展開する
米国を選択

[![Deploy to Koyeb](https://www.koyeb.com/static/images/deploy/button.svg)](https://app.koyeb.com/deploy?type=docker&name=aurora&ports=8080;http;/&image=ghcr.io/aurora-develop/aurora)

### Railway展開する
[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/jcl2Es?referralCode=XXqY_5)

### Zeabur展開する
画像名を変更するには、Aurora +任意の英数字を入力してください

[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/JF3EFW)

### コンパイルとデプロイ

```bash
git clone https://github.com/aurora-develop/aurora
cd aurora
go build -o aurora
chmod +x ./aurora
./aurora
```

### Docker展開する
## Docker展開する
Docker と Docker Compose がインストールされている必要があります。

```bash
docker run -d \
  --name aurora \
  -p 8080:8080 \
  ghcr.io/aurora-develop/aurora:latest
```

## Docker Compose展開する
新しいディレクトリ (例: aurora-app) を作成し、そこに移動します。
```bash
mkdir aurora
cd aurora
```
このディレクトリに docker-compose.yml ファイルをダウンロードします。

```bash
docker-compose up -d
```

## Usage

```bash
curl --location 'http://你的服务器ip:8080/v1/chat/completions' \
--header 'Content-Type: application/json' \
--data '{
     "model": "gpt-3.5-turbo",
     "messages": [{"role": "user", "content": "Say this is a test!"}],
     "stream": true
   }'
```

## 詳細設定

デフォルトでは、必要がない限り設定は必要ありません。

### 環境変数
```

BASE_URL="https://chat.openai.com/backend-api" プロキシゲートウェイ
Authorization=your_authorization  ユーザー認証 key。
TLS_CERT=path_to_your_tls_cert TLS (トランスポート層セキュリティ) 証明書を保存するパス。
TLS_KEY=path_to_your_tls_key TLS (トランスポート層セキュリティ) 証明書を保存するパス。
PROXY_URL=your_proxy_url プロキシ プールを に追加します。
```

## 謝辞

皆様のPRのご支援、誠にありがとうございます。


## 参照プロジェクト


https://github.com/xqdoo00o/ChatGPT-to-API

## License

MIT License
