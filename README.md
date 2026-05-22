# 🏔️ Demal - Clean Air App

![iOS 17.0+](https://img.shields.io/badge/iOS-17.0%2B-blue.svg)
![Swift 6](https://img.shields.io/badge/Swift-6.0-orange.svg)
![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-success.svg)
![Architecture MVVM](https://img.shields.io/badge/Architecture-MVVM-lightgrey.svg)
![License MIT](https://img.shields.io/badge/License-MIT-green.svg)

## 📖 О проекте

Алматы известен своими величественными горами, но, к сожалению, в осенне-зимний период город часто накрывает плотный смог. **Demal** (от казахского *демалу* — дышать, отдыхать) — это iOS-приложение, созданное для мотивации жителей мегаполиса чаще выбираться на природу. 

Приложение в реальном времени мониторит качество городского воздуха (AQI) и, если дышать становится тяжело, предлагает пользователю идеальные локации высоко в горах (Медеу, Шымбулак, Кок-Жайляу), где прямо сейчас светит солнце и чистый воздух.

## ✨ Ключевые возможности

- **Live AQI Tracking:** Ежеминутный мониторинг уровня смога в городе на основе данных Open-Meteo.
- **Mountain Weather:** Актуальная погода, температура и облачность на горных пиках (через Meteosource API).
- **Smart Navigation:** Интерактивная карта с возможностью построения автомобильного маршрута от текущей геопозиции пользователя прямо до выбранного горного курорта (MapKit + CoreLocation).
- **Favorites Storage:** Сохранение любимых локаций в профиль для быстрого доступа.

## 🚀 Быстрый старт

### Требования
* Xcode 16.0+
* iOS 17.0+
* macOS для разработки
* Сборка с включенным `Strict Concurrency: Complete`

### Установка и запуск

1. Склонируйте репозиторий:
```bash
git clone [https://github.com/ВАШ_НИК/Demal-App.git](https://github.com/Kissly1/Demal-App.git)

2. Перейдите в папку проекта:

cd Demal-App

3. Откройте проект в Xcode:

open Demal.xcodeproj

4. Выберите симулятор (рекомендуется iPhone 17 Pro / iOS 17+) и нажмите Cmd + R (▶️ Play).


🏗️ Архитектура и Технологии
Проект построен на современной архитектуре MVVM с полным отказом от старых подходов (никакого UIKit).

UI: 100% SwiftUI с активным использованием Glassmorphism (.ultraThinMaterial).

State Management: Макрос @Observable (нативный реактивный подход iOS 17+).

Concurrency: Swift 6 Concurrency (async/await, @MainActor, TaskGroups для безопасных параллельных сетевых запросов).

Data Safety: actor StorageManager для потокобезопасного кэширования избранного.

Map & Location: Нативный iOS 17 Map() API и MKDirections.

🔧 Структура проекта


Demal/
├── App/
│   └── DemalApp.swift                # Точка входа и Environment инъекции
├── Models/
│   └── Location.swift                # Codable структуры ответов API
├── ViewModels/
│   ├── DashboardViewModel.swift      # Бизнес-логика главного экрана
│   └── ProfileViewModel.swift        # Логика пользователя
├── Services/
│   ├── APIService.swift              # Сетевой слой (Meteosource, Open-Meteo)
│   └── LocationManager.swift         # Обертка над CoreLocation
└── Views/
    ├── DashboardView.swift           # Главный дашборд
    ├── MapView.swift                 # Интерактивная карта с маршрутами
    └── Components/                   # Переиспользуемые элементы UI



    🎨 Design System
Background: rgb(0.08, 0.09, 0.12) → rgb(0.10, 0.11, 0.16)

Accent Orange: rgb(1.0, 0.45, 0.2)

AQI Colors: * Good 🟢 rgb(0.2, 0.8, 0.4)

Unhealthy 🔴 rgb(1.0, 0.35, 0.2)

🚧 Roadmap
Phase 1: UI & Architecture ✅

[x] MVVM сетап и дизайн-система

[x] SwiftUI верстка (Dashboard, Map, Profile)

[x] Строгая настройка Swift 6 Concurrency

Phase 2: Networking & Real Data ✅

[x] Интеграция Meteosource API (Погода в горах)

[x] Интеграция Open-Meteo API (Live AQI в городе)

[x] CoreLocation для текущей позиции пользователя

[x] Обработка ошибок сети и изоляция сбоев

Phase 3: Features & Polish (В планах) ⏳

[ ] Push-уведомления при высоком уровне AQI

[ ] Кэширование истории посещений через SwiftData

[ ] Локализация (EN / RU / KZ)

👨‍💻 Разработчики
Alexander Kisslitsyn * Alikhan Amangeldiyev 📍 Almaty, Kazakhstan 🇰🇿 | Май 2026

MIT License
