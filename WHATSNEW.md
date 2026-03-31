# What's New in SqlPulse

**v0.1.248 - 2026-03-31**

---

### Added
- **Dependency Viewer** — new window showing what a database object depends on and what uses it; supports direct (one-level) and recursive (full chain) modes; definition panel scripts the selected dependency inline
- **Object Search: View Dependencies** — "View Dependencies" button on selected search results opens the Dependency Viewer for that object
- **Editor context menu: View Dependencies** — SqlPulse → View Dependencies opens the Dependency Viewer directly from selected object name in any query editor
- **Version check

### Changed
- SMO scripting logic centralized into `ScriptObjectExecutor`; duplicate code removed from `ScriptObjectCommand` and `QueryEditorContextMenuInjector`
- `SqlObjectType.ToSmoCollection()` added as single source of truth for type → SMO collection mapping
- `SearchSmoHelper` delegation to `SmoScriptingService` fixed (was silently falling back to standalone mode inside SSMS due to wrong overload signature)
- Fix codeinspector

---

---

[Back to README](README.md)
