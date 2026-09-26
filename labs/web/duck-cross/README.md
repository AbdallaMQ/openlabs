# duck-cross

`easy` · `web`

## Brief

The duck cross portal collects crossing reports from wardens. Five reports are public. One report stays restricted. Read it.

## Setup

Run these from the lab directory:

```bash
docker compose up -d
```

Open `http://localhost:8377`.

## Goal

Find the restricted report. Extract its flag. Verify the solve from the lab directory:

```bash
python3 ../../../scripts/check.py .
```

## Reference lifecycle

This lab is the repository reference for M0 L0–L6 evidence.

| Level | Check |
|:---:|:---|
| L0 | `lab.yml`, required files, and validator metadata |
| L1 | `docker compose config` exposes port `8377` |
| L2 | `docker compose build` from a clean checkout |
| L3 | Service ready within 60 seconds at `http://127.0.0.1:8377` |
| L4 | Player page loads and a public report API call succeeds |
| L5 | Intended IDOR path reaches the flag; `scripts/check.py` accepts it |
| L6 | `docker compose down -v` removes namespaced resources; a second start passes |

CI runs `python3 scripts/prove_reference_lab.py` with compose project
`openlabs-ref-duck-cross`. Logs redact flag values on failure.

Reset locally:

```bash
docker compose -p openlabs-ref-duck-cross down -v
```
