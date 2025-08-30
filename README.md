# Dynamic Data Ingestion → HDFS with Automated Hive Integration


**What it does**
- Fetch a dataset from any URL (CSV preferred)
- Land it in HDFS (idempotent overwrite)
- Create an **EXTERNAL** Hive table pointing to that file/dir
- Optional: cron schedule for daily refresh


## Prereqs
- Hadoop client tools in PATH: `hdfs`
- HiveServer2 client: `beeline`
- `curl`, `sed`, `python3`
- Hive OpenCSVSerde available (common in modern Hive distros)


## Quickstart
```bash
# 1) Configure
cp .env.example config/pipeline.env
vim config/pipeline.env # set DATA_URL, HDFS_DIR, HIVE_DB/TABLE


# 2) Run end-to-end
python3 pipeline.py
