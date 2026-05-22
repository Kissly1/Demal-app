# 🏔️ Demal - Clean Air App

![iOS 17.0+](https://img.shields.io/badge/iOS-17.0%2B-blue.svg)
![Swift 6](https://img.shields.io/badge/Swift-6.0-orange.svg)
![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-success.svg)
![Architecture MVVM](https://img.shields.io/badge/Architecture-MVVM-lightgrey.svg)
![License MIT](https://img.shields.io/badge/License-MIT-green.svg)

**Demal** — это iOS-приложение, созданное для мотивации жителей Алматы (и других мегаполисов) выбираться из городского смога на свежий горный воздух. Приложение в реальном времени отслеживает качество воздуха в городе и предлагает локации в горах с идеальной погодой и чистым небом.

## ✨ Ключевые возможности

- **Live AQI Tracking:** Реальные данные о смоге в городе (через Open-Meteo).
- **Mountain Weather:** Актуальная погода на горных пиках (Meteosource API).
- **Smart Navigation:** Построение маршрутов от текущей геопозиции пользователя прямо до горного курорта (MapKit + CoreLocation).
- **Favorites Storage:** Сохранение любимых локаций с использованием строгой многопоточности (Actors).

## 🚀 Быстрый старт

### Требования
* Xcode 16.4+
* iOS 17.0+
* macOS для разработки

### Установка и запуск

1. Склонируйте репозиторий:
```bash
git clone [https://github.com/ВАШ_НИК/Demal-App.git](https://github.com/Kissly1/Demal-App.git)

Перейдите в папку проекта:


cd Demal-App


Откройте проект в Xcode:


open Demal.xcodeproj


Выберите симулятор (рекомендуется iPhone 17 / iOS 17+) и нажмите Cmd + R (▶️ Play).

🏗️ Архитектура и Технологии
Проект построен на современной архитектуре MVVM с полным отказом от старых подходов (никакого UIKit).

UI: 100% SwiftUI с активным использованием Glassmorphism (.ultraThinMaterial).

State Management: Макрос @Observable (нативный подход iOS 17+).

Concurrency: Swift 6 Concurrency (async/await, @MainActor, TaskGroups для параллельных сетевых запросов).

Data Safety: actor StorageManager для потокобезопасного кэширования.

Map & Location: Нативный iOS 17 Map() API и MKDirections.

🔧 Структура проекта
Plaintext
Demal/
├── App/
│   └── DemalApp.swift                # Точка входа и Environment инъекции
├── Models/
│   └── Location.swift                # Codable структуры ответов API
├── ViewModels/
│   ├── DashboardViewModel.swift      # Бизнес-логика главного экрана
│   └── ProfileViewModel.swift        # Логика пользователя и избранного
├── Services/
│   ├── APIService.swift              # Сетевой слой (Meteosource, Open-Meteo)
│   └── LocationManager.swift         # Обертка над CoreLocation
└── Views/
    ├── DashboardView.swift           # Главный дашборд
    ├── MapView.swift                 # Интерактивная карта
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

[x] Строгая настройка Concurrency

Phase 2: Networking & Real Data ✅

[x] Интеграция Meteosource API (Погода в горах)

[x] Интеграция Open-Meteo API (Live AQI в городе)

[x] CoreLocation для текущей позиции пользователя

[x] Обработка ошибок сети и фоллбэки

Phase 3: Features & Polish (В планах) ⏳

[ ] Push-уведомления при высоком уровне AQI

[ ] Кэширование истории через SwiftData

[ ] Локализация (EN / RU / KZ)

👨‍💻 Разработчики
Alexander Kisslitsyn * Alikhan Amangeldiyev 📍 Almaty, Kazakhstan 🇰🇿 | Май 2026

MIT License
