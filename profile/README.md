<div align="center">

# 🛠️ 2Xsave Organization
**High-performance media research & automation engines powered by Rust**

[![Organization](https://img.shields.io/badge/Org-2Xsave-blueviolet?style=for-the-badge&logo=github)](https://github.com/2Xsave)
[![Tech Stack](https://img.shields.io/badge/Stack-Rust%20%7C%20Python-orange?style=for-the-badge)](https://rust-lang.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](https://opensource.org/licenses/MIT)

---
<p align="center">
  <a href="#-projects">Projects</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-tech-stack">Stack</a> •
  <a href="#-roadmap">Roadmap</a>
</p>

</div>

## 📖 О нас

**2Xsave** — исследовательская группа, специализирующаяся на глубоком анализе медиаплатформ. Мы превращаем сложные реверс-инжиниринговые задачи в элегантные и быстрые инструменты на Rust.

> [!CAUTION]
> **Disclaimer:** Наши инструменты предназначены исключительно для образовательных целей и личного использования. Мы не поддерживаем пиратство.

---

## 🚀 Projects

Мы упаковываем каждый сервис в отдельное «ядро» (`core`), которое можно использовать как CLI-утилиту или библиотеку.

| Platform | Repository | Status | Engine |
| :--- | :--- | :--- | :--- |
| **TikTok** | [`ttsave_core`](https://github.com/2Xsave/ttsave_core) | ![Active](https://img.shields.io/badge/-active-success?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |
| **Instagram** | [`insave_core`](https://github.com/2Xsave/insave_core) | ![Active](https://img.shields.io/badge/-active-success?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |
| **Threads** | [`trsave_core`](https://github.com/2Xsave/trsave_core) | ![Active](https://img.shields.io/badge/-active-success?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |
| **X (Twitter)** | [`twsave_core`](https://github.com/2Xsave/twsave_core) | ![Active](https://img.shields.io/badge/-active-success?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |
| **SoundCloud** | [`sksave_core`](https://github.com/2Xsave/sksave_core) | ![Active](https://img.shields.io/badge/-active-success?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |
| **Common** | [`2xsave_common`](https://github.com/2Xsave/2xsave_common) | ![Stable](https://img.shields.io/badge/-stable-blue?style=flat-square) | ![Rust](https://img.shields.io/badge/-Rust-brown?style=flat-square&logo=rust) |

---

## 🏗 Architecture

Наша экосистема построена на принципе **"Three-Tier Access"**:

```mermaid
graph LR
    A[Rust Core] --> B[CLI Tool]
    A --> C[Native Rust Crate]
    A --> D[Python Module via PyO3]

```

* **⚡ Speed:** Нулевая стоимость абстракций.
* **🐍 Versatility:** Используйте мощь Rust в своих Python-скриптах.
* **🛠 Modular:** Общая логика в `2xsave_common` обеспечивает единство API.

---

## 🛠 Tech Stack

Мы используем только самый современный и безопасный инструментарий:

* **Languages:**


* **Async:** [Tokio](https://tokio.rs/) — мощный асинхронный движок.
* **FFI:** [PyO3](https://pyo3.rs/) — бесшовная интеграция Rust в Python.
* **Net:** [Reqwest](https://docs.rs/reqwest) + [Serde](https://serde.rs/) — надежная работа с API и JSON.

---

## 📅 Roadmap

* [ ] **AMSAVE:** Исследование Apple Music API (Web Player).
* [ ] **SPOTIFY:** Начало разработки универсального парсера метаданных.
* [ ] **CLI-UNIFY:** Единая оболочка для управления всеми модулями из одного терминала.
* [ ] **WEB-API:** Опциональный легковесный прокси-сервер для модулей.

---

## 🛡 Non-goals

Мы **НЕ** занимаемся следующими вещами:

1. Обход DRM или систем защиты платного контента.
2. Нарушение приватности пользователей.
3. Создание инструментов для массового спама или деструктивных действий.

---
