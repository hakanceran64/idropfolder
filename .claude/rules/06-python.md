# Kural 06: Python Konvansiyonları

**Severity:** error · **Stages:** `**/*.py`
**Kaynak:** developer-toolkit `python-package` template (genelleştirildi)

## Stack kararları (toolchain)

> **Toolchain sürümlerinin kanonik kaynağı:** `devkit-wiki/registry/stack-registry.yaml`
> (profil `python`). Aşağıdaki tablo oradan türetilmiştir — sürüm değişecekse
> **önce registry'de** değiştir, sonra burayı güncelle. `lint-wiki.sh` registry'nin
> bu profile ve template'e gerçekten işaret ettiğini doğrular.


| Karar | Seçim |
|-------|-------|
| build | hatchling (`pyproject.toml` `[build-system]`) |
| dil sürümü | Python **3.11+** (`requires-python = ">=3.11"`) |
| lint | `ruff check` (`select = ["E","F","I","W","B"]`) + `mypy` (opsiyonel) |
| format | `ruff format` (line-length **100**) |
| test | `pytest` (`testpaths=["tests"]`, `pythonpath=["src"]`) |
| pkg-mgr | pip (pyproject) — opsiyonel `uv`/`poetry` |
| layout | **src-layout**: `src/<pkg>/` · `tests/` |
| config | tek dosya: `pyproject.toml` |

## Stil & yapı

- **src-layout** zorunlu: paket `src/<pkg>/`, testler `tests/`. Import'lar mutlak (`from pkg.mod import x`).
- **Type hint** her public fonksiyon/metotta; `mypy` temiz hedeflenir. `Any` yerine `typing`/`Protocol`.
- **Docstring** modül/sınıf/public fonksiyonda (kısa, "neden" odaklı; kodu tekrar etmez).
- İsimlendirme PEP 8: `snake_case` fonksiyon/değişken, `PascalCase` sınıf, `BÜYÜK_HARF` sabit.

## Hata & kaynak yönetimi

- Spesifik exception yakala (`except Exception` değil); bağlamı koru (`raise ... from err`).
- Kaynaklar `with` (context manager) ile; dosya/socket sızıntısı yok.
- I/O sınırında girdi doğrulama (pydantic/dataclass + validation); `assert` ile iş kuralı zorlanmaz.

## Test

- `pytest`; fixture'lar `conftest.py`'de; parametrize ile tablo-test. Kritik yollar kapsanır.
- Dış I/O mock'lanır; testler deterministik ve hermetik.

## İlgili

- Çekirdek: [05-kod-kalitesi](05-kod-kalitesi.md)
- Stack/bootstrap kararları: `claude-foundation/docs/NEW-PROJECT-DECISIONS.md`
