# NaosBinary – Benchmark Summary

This document provides a short, human-readable summary of the benchmark results.
Raw benchmark files are available in this directory.

---

## Auto mode – 100,000 bits

### all_ones pattern
- Input size: 12,500 bytes
- Output size: 5 bytes
- Compression ratio: ~0.0004 (≈ ×3000)
- Selected mode: RLE-1

### random data
- Compression ratio: ~1.0003
- Selected mode: BitPack (clean bypass)

### blocky data
- Compression ratio: ~1.0003
- Selected mode: BitPack (clean bypass)

---

## Latency – 2048-bit blocks

### random
- Encode latency: ~0.19 ms
- Decode latency: ~0.18 ms
- Selected mode: BitPack

### blocky
- Encode latency: ~0.18–0.20 ms
- Decode latency: ~0.17–0.20 ms
- Selected mode: BitPack

---

## Notes

- No data corruption observed (roundtrip validated)
- No catastrophic expansion on high-entropy data
- Automatic mode selection behaves deterministically
