# idropfolder — Claude Code Context

> Bu dosya ekosistem rollout'unda **registry'den bilinen gerçeklerle** üretildi
> (2026-08-03). İçindeki her şey doğrulanmıştır; eksik olan yerler aşağıdaki
> "Genişlet" bölümünde açıkça listelenmiştir — uydurma bilgi yoktur.

## Özet

iDropFolder, iPhone’daki seçtiğiniz fotoğraf ve videoları Windows 11 bilgisayardaki bir klasöre kablosuz olarak yüklemek için hazırlanmıştır.

- **Teknoloji:** Python 3.11+ · ruff · pytest · hatchling
- **Çalışma dizini:** `/Users/ceran/Backup/GitHub/idropfolder`
- **Ekosistem profili:** python

- Son commit: 2026-06-18 · Commit sayısı: 4 · Remote: origin

## Repoda tespit edilenler

- Python bağımlılıkları (requirements.txt)

## Kurallar (bağlayıcı)

`.claude/rules/` altındaki dosyalar **otomatik yüklenir** ve bağlayıcıdır:

- `01-dil` — çıktı Türkçe, kod/commit İngilizce
- `02-guvenlik` — yıkıcı operasyonlar onay/yasak
- `03-commit` — Conventional Commits, AI atfı YOK
- `04-izinler` — izin matrisi
- `05-kod-kalitesi` — SOLID · Clean Code · anti-pattern yasakları
- `06-python` — Python 3.11+ · ruff · pytest · hatchling

## Ekosistem

Bu repo CERAN Development Ecosystem üyesidir. Ne tükettiği
`.ceran/ecosystem.yaml`'da beyan edilir, ne kurulu olduğu
`.ceran/lock.yaml`'da yazar (üretilen — elle düzenlenmez).

```bash
dev eco status          # ne kurulu, drift var mı
dev eco sync --check    # ekosistemle uyumlu mu (CI)
dev eco sync            # merkez güncellemelerini al
```

## `.claude` altyapısı

| Bileşen | Yer |
|---------|-----|
| Kurallar | `.claude/rules/` |
| Skills | `.claude/skills/` — `/audit`, `/adr`, `/commit-push-pr`, `/changelog-draft`, `/mermaid-check` |
| Agents | `.claude/agents/` |
| Hooks | `.claude/hooks/` |
| Memory | `.claude/memory/` (+ `MEMORY.md` index) |

## Genişlet (bu dosyanın bilmediği şeyler)

Aşağıdakiler otomatik üretilemez — projeyi bilen kişi doldurur:

- Projenin amacı ve hedef kitlesi (bir-iki cümle)
- Mimari katmanlar ve aralarındaki bağımlılık yönü
- Kurulum / build / test komutları
- Kritik mimari kararlar ve gerekçeleri (varsa `docs/adr/`'ye ADR olarak)
- Bilinen tuzaklar / gotcha'lar

---
**Governance:** Bu projenin `.claude/**` veya `CLAUDE.md` dosyaları değişirse
`claude-config-watcher` hook'u durumu operatöre ve `claude-foundation`'a bildirir.
