# ALICE-Token SaaS

Ultra-fast BPE tokenizer API for text tokenization

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Token |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/tokenize` | テキストをトークンID列に変換 |
| `POST /api/v1/detokenize` | トークンID列をテキストに復元 |
| `GET  /api/v1/vocab` | 語彙情報取得 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
