# mvp-plan-generator
## 🛠️ Skills zu Claude hinzufügen

Skills sind Ordner mit Anleitungen (`SKILL.md`), die Claude automatisch nutzt, wenn sie relevant sind — z.B. für wiederkehrende Workflows, Coding-Konventionen oder Domain-Wissen.

### 1. Skill in claude.ai hinzufügen

1. Gehe zu **Settings** in claude.ai <br/>
   <img width="402" height="80" alt="Bildschirmfoto 2026-07-13 um 19 00 30" src="https://github.com/user-attachments/assets/6c4ab885-890e-4a8e-8fee-849e3153b93e" />
2. Dort Skills-Bereich öffnen <br/>
   <img width="185" height="322" alt="image" src="https://github.com/user-attachments/assets/a743c94c-d662-4150-be3a-5a5824ddc1cd" />
3. Skill-Ordner (als `.zip` oder einzelne Dateien) hochladen <br/>
   <img width="127" height="42" alt="image" src="https://github.com/user-attachments/assets/117d37f8-8207-4904-9096-fdca94904b9e" /> <br/>
   <img width="240" height="68" alt="image" src="https://github.com/user-attachments/assets/7e8679d7-5712-4f02-ae89-a8a3f9b01f46" />


### 2. Skill-Struktur

Jeder Skill ist ein Ordner mit einer `SKILL.md` Datei, die mit YAML-Frontmatter beginnt:

```
my-skill/
└── SKILL.md
```

```markdown
---
name: my-skill-name
description: Kurze, klare Beschreibung was der Skill tut und wann er genutzt werden soll
---

# My Skill Name

[Hier die Anleitung, die Claude befolgen soll, wenn der Skill aktiv ist]

## Examples
- Beispiel 1
- Beispiel 2

## Guidelines
- Guideline 1
- Guideline 2
```

Die `description` ist entscheidend — Claude entscheidet anhand davon, wann der Skill getriggert wird. Je konkreter, desto besser.

### 3. Skill in Claude Code hinzufügen

**Für dieses Projekt** (im Repo, teilbar via Git):
```bash
mkdir -p .claude/skills/my-skill-name
```
→ `SKILL.md` dort ablegen. Wird automatisch geladen, sobald Claude Code im Projekt läuft.

**Für alle deine Projekte** (persönlich, nicht im Repo):
```bash
mkdir -p ~/.claude/skills/my-skill-name
```

Claude Code erkennt Änderungen an bestehenden Skills automatisch (ohne Neustart). Wird ein komplett **neuer** `skills/`-Ordner angelegt, braucht es einen Neustart der Session, damit er erkannt wird.

### 4. Testen

Frag Claude einfach nach einer Aufgabe, die zur `description` deines Skills passt. Wenn der Skill nicht triggert, ist meist die Beschreibung zu vage — konkreter formulieren und erneut testen.

---
📚 Mehr Details: [Anthropic Agent Skills Docs](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)

