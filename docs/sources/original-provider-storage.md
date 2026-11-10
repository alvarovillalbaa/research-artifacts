## Provider Interface

Every provider adapter should implement:

```text
submit_job()
cancel_job()
get_logs()
get_metrics()
sync_data()
upload_checkpoint()
download_checkpoint()
launch_endpoint()
stop_endpoint()
estimate_cost()
```

## Canonical Storage Rule

Object storage is the source of truth.

- Local NVMe is cache.
- Parallel filesystems are performance optimizations.
- Provider-specific paths must never be the only copy.
- Every dataset shard, tokenizer, checkpoint, and eval result must have a hash.
