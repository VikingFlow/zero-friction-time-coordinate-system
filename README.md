# Zero-Friction Time Coordinate System (ZFTCS)

A deterministic, human-readable temporal index system for zero-friction context linking, storage, log-keeping, and multi-AI workflows.

---

## Why ZFTCS exists — The Reinforced Concrete Analogy

```
┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳
┃ Concrete = The temporal structure     ┃
┃ (YYYY-Www-D-HHMMSS-ssssss-POD)        ┃
┃ → provides stability, determinism,    ┃
┃   chronological integrity,            ┃
┃   load-bearing strength               ┃
┃                                       ┃
┃ Rebar = ANI + metadata                ┃
┃ (adjective-noun-index + tags)         ┃
┃ → provides semantic strength,         ┃
┃   flexibility, crack prevention       ┃
┃                                       ┃
┃ Together = Zero-Friction              ┃
┃ infrastructure that lasts 20–30 years ┃
┃ without rebuilding.                   ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛
```

ZFTCS is not “just another timestamp” — it is **construction material** for robust, future-proof context management.

---

## ZFTCS v1.0 — Formal Specification

### **Primary Key Format (ZFTCS-ID)**

```
YYYY-Www-D-HHMMSS-ssssss-POD-ANI
```

| Field | Meaning | Required |
|------|---------|----------|
| `YYYY` | Year (UTC) | Yes |
| `Www` | ISO week (W01–W53) | Yes |
| `D` | Weekday (1–7, Monday=1) | Yes |
| `HHMMSS` | 24h time | Yes |
| `ssssss` | Microseconds (000000–999999) | Yes |
| `POD` | Part-of-Day (MORN, DAY, EVE, NIGHT) | Yes |
| `ANI` | Adjective-Noun-Index | Optional |

**Example:**

```
2025-W48-4-193045-873192-EVE-fast-learning
```

---

## Part-of-Day (POD)

| POD  | Time (UTC)         |
|------|---------------------|
| MORN | 05:00–11:59         |
| DAY  | 12:00–17:59         |
| EVE  | 18:00–22:59         |
| NIGHT| 23:00–04:59         |

---

## ANI — Adjective-Noun Index (optional)

Rules:

- 1–3 adjectives + 1 noun  
- lowercase letters, numbers, hyphens  
- max 12 characters  
- no accents (no åäö etc.)  
- concise but semantic  

Examples:

```
fast-learning
deep-focus
hardware-test
grok-debate
```

---

## Indexing Rules

- Every event receives **exactly one** ZFTCS-ID.  
- IDs are **immutable**.  
- One event must never have two IDs.  
- ANI may be omitted:

```
2025-W48-4-193045-873192-EVE-
```

---

## Sorting Order

ZFTCS sorts correctly with **plain string sorting**:

```
2025-W48-4-193045-873192-EVE-fast-learning
2025-W48-4-193046-000123-EVE-slow-think
2025-W48-5-090123-445566-MORN-new-idea
```

---

## Recommended Data Structure

```json
{
  "zftcs": "2025-W48-4-193045-873192-EVE-fast-learning",
  "timestamp_utc": "2025-11-27T19:30:45.873192Z",
  "content": "Full text, log, message, or binary blob here.",
  "source": "grok|chatgpt|human|sensor",
  "tags": ["robot", "stresstest", "v2"],
  "hash": "sha256:ab1f2e..."
}
```

---

## Use Cases

### 🔹 Multi-AI Stress Labs  
Precise alignment between responses from multiple AI systems.

### 🔹 Zero-Friction Context Linking  
Human-readable, deterministic anchors for logs and workflows.

### 🔹 Research & Science Logs  
Designed for multi-year chronological projects.

### 🔹 Agent Memory Indexing  
Lightweight, universal, deterministic.

### 🔹 Multi-device Synchronization  
No parsing needed; works across all systems.

---

## Roadmap

- v1.1: Python class + CLI generator  
- v1.2: Mermaid diagrams  
- v2.0: Canonical registry + cryptographic binding  

---

## License

Released under **Apache License 2.0**.

---

## Maintainer

**VikingFlowAI**
