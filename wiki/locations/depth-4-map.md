# Depth 4 — Dungeon Map

*Room reference map. For full room descriptions see [[depth-4]].*

```mermaid
graph TD
    STAIRS([" ▼ STAIRCASE DOWN "]):::entry --> R1

    R1["**R1** · Entry Hall\n3-way junction"]
    R1 --> R2["**R2** · West Dead End\nDead end"]
    R1 --> R3["**R3** · North Corridor\n⚠ Pressure Plate Trap"]
    R1 --> R4["**R4** · East Alcove\nKobold workstation"]

    R3 --> R5["**R5** · Wide Cavern\nSakapatate sighting"]
    R5 --> R6["**R6** · The Narrows\n⚠ Tripwire Alarm"]
    R6 --> R7["**R7** · Outer Ward\nKobold patrol"]

    R7 -->|"⛔ KOBOLD GUARD"| R8["**R8** · Red Corridor\n🩸 Blood drainage\nUpper Hammerfall beyond"]:::sealed
    R7 --> R9["**R9** · Settlement Gate\nArched entry"]

    R9 --> R10["**R10** · Matriarch's Hall\n👑 Vress · Skit\nKobold settlement"]:::major

    R10 --> R11["**R11** · Storage\n📦 Freya objects\n→ Hollow Coin hook"]
    R10 --> R12["**R12** · Forge Room\nKobold smiths"]
    R10 --> R13["**R13** · Workshop\nTrap engineer"]
    R10 --> R14["**R14** · Deep Passage\nStonework gives way to cave"]

    R14 --> R15["**R15** · Odin Temple\nPlain room · One-eye puzzle"]:::temple
    R15 --> R16["**R16** · Odin's Sanctum\n🗝 RUNE 6/8"]:::rune

    R14 --> R17["**R17** · Freya Entrance\n🔒 SEALED · No mechanism\n→ Hollow Coin / Richeri"]:::sealed

    R14 --> R18["**R18** · Thor Temple\nFlooded · Magnetic pillars\nStorm Warden combat"]:::temple
    R18 --> R19["**R19** · Thor Rune\n🗝 RUNE 7/8"]:::rune

    classDef entry fill:#2a2a2a,color:#ccc,stroke:#666
    classDef sealed fill:#5a0000,color:#ffaaaa,stroke:#900
    classDef major fill:#2a3a5a,color:#aaccff,stroke:#446
    classDef temple fill:#3a2a5a,color:#ccaaff,stroke:#648
    classDef rune fill:#1a4a2a,color:#aaffcc,stroke:#484
```

---

## Quick Reference

| Key | Room | Status |
|-----|------|--------|
| R1 | Entry Hall | Junction |
| R2 | West Dead End | Dead end |
| R3 | North Corridor | ⚠ Trap |
| R4 | East Alcove / Workstation | Exploration |
| R5 | Wide Cavern | Sakapatate sighting |
| R6 | The Narrows | ⚠ Trap/alarm |
| R7 | Outer Ward | Kobold patrol |
| R8 | Red Corridor | ⛔ Kobold-sealed |
| R9 | Settlement Gate | Transition |
| R10 | Matriarch's Hall | 👑 Social hub |
| R11 | Storage | 📦 Freya hook items |
| R12 | Forge Room | RP |
| R13 | Workshop | RP |
| R14 | Deep Passage | Temple junction |
| R15 | Odin Temple | 🧩 Puzzle |
| R16 | Odin's Hidden Sanctum | 🗝 Rune 6/8 |
| R17 | Freya Entrance | 🔒 Sealed |
| R18 | Thor Temple | ⚔ Combat |
| R19 | Thor Rune | 🗝 Rune 7/8 |
