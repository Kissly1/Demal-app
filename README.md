# Demal - Clean Air App 🏔️

Приложение для мотивации жителей Алматы выбраться из городского смога в чистый горный воздух.

## 🚀 Быстрый старт

### Требования
- Xcode 16.4+ (26.4)
- iOS 17.0+
- macOS для разработки

### Запуск проекта

1. Откройте проект в Xcode:
```bash
cd /Users/alexandrkisslitsyn/Desktop/Demal
open Demal.xcodeproj
```

2. Выберите симулятор: **iPhone 17** (или любой iOS 17+)

3. Нажмите **⌘R** или кнопку ▶️ Play

## 📱 Экраны приложения

### 1️⃣ Dashboard (Home)
- Круговой AQI индикатор текущей локации
- Glassmorphism карточка "Escape the Smog"
- Сетка метрик погоды (Wind, Visibility, Cloud Cover, Feels Like)
- Список горных локаций с чистым воздухом

### 2️⃣ Locations List
- Поиск по локациям (`.searchable`)
- Разделение на города и горы
- Кнопки Pin/Share для действий

### 3️⃣ Location Detail
- Детальная информация о AQI
- Полные метрики воздуха (PM2.5, PM10, O3, NO2)
- Погода и высота над уровнем моря

### 4️⃣ Map View
- Интерактивная карта с пинами локаций
- Переключение между картой и списком

### 5️⃣ Profile
- Настройки уведомлений
- История посещений гор
- Статистика "дыхания чистым воздухом"

## 🏗️ Архитектура

```
MVVM (Model-View-ViewModel)
├── Models: Чистые Swift структуры (Codable, Hashable)
├── ViewModels: @Observable (iOS 17+), @MainActor
└── Views: SwiftUI компоненты (без логики)
```

### Ключевые технологии
- ✅ **SwiftUI** (100%, без UIKit)
- ✅ **@Observable macro** (iOS 17+, не ObservableObject)
- ✅ **Swift 6 Concurrency** (@MainActor, async/await)
- ✅ **Glassmorphism** (.ultraThinMaterial)
- ✅ **SF Symbols** для иконок
- ✅ **MapKit** для карты

## 📊 Mock Data (Phase 1)

### Города (Плохой воздух)
| Локация | AQI | PM2.5 | Температура |
|---------|-----|-------|-------------|
| Almaty City Center | 158 🔴 | 67.8 | -3°C |
| Orbita | 145 🔴 | 61.3 | -2.5°C |
| Mikrorayon | 162 🔴 | 70.1 | -3.2°C |

### Горы (Чистый воздух)
| Локация | AQI | PM2.5 | Температура | Высота |
|---------|-----|-------|-------------|--------|
| Shymbulak | 12 🟢 | 4.8 | -8°C | 2260m |
| Medeu | 18 🟢 | 7.2 | -5°C | 1691m |
| Kok Zhailau | 8 🟢 | 3.2 | -6.5°C | 1800m |
| Chimbulak Peak | 5 🟢 | 2.1 | -12°C | 3200m |

## 🔧 Структура файлов

```
Demal/
├── DemalApp.swift                    # @main точка входа
├── ContentView.swift                 # Root view
├── Models/
│   ├── Location.swift                # Domain модели
│   └── MockData.swift                # Статические данные
├── ViewModels/
│   ├── DashboardViewModel.swift      # Главный экран VM
│   └── LocationsViewModel.swift      # Список локаций VM
└── Views/
    ├── DashboardView.swift           # Home screen
    ├── LocationsListView.swift       # Список + поиск
    ├── LocationDetailView.swift      # Детали локации
    ├── MapView.swift                 # Карта
    ├── ProfileView.swift             # Профиль
    ├── MainTabView.swift             # Tab bar
    └── Components/
        ├── AQIGaugeView.swift        # Круговой индикатор
        ├── EscapeCardView.swift      # Карточка предложения
        ├── LocationRowView.swift     # Строка списка
        └── WeatherMetricTileView.swift # Плитка погоды
```

## 🎨 Design System

### Цветовая палитра
- **Background**: `rgb(0.08, 0.09, 0.12)` → `rgb(0.10, 0.11, 0.16)`
- **Accent Orange**: `rgb(1.0, 0.45, 0.2)`
- **Good AQI**: `rgb(0.2, 0.8, 0.4)` 🟢
- **Unhealthy AQI**: `rgb(1.0, 0.35, 0.2)` 🔴

### Типографика
- **Title**: `.title` / Bold
- **Headline**: `.headline` / Semibold
- **Body**: `.body` / Regular
- **Caption**: `.caption` / Regular

## 🐛 Исправленные ошибки

См. [PHASE1_SUMMARY.md](./PHASE1_SUMMARY.md) для детального списка.

### Основные исправления:
1. ✅ Создан отсутствующий `MockData.swift`
2. ✅ Исправлены ссылки в `DashboardViewModel`
3. ✅ Исправлен синтаксис форматирования в `DashboardView`

## 📦 Build Status

```bash
** BUILD SUCCEEDED **
```

- ✅ 0 ошибок
- ✅ 0 предупреждений
- ✅ 16 Swift файлов компилируются

## 🚧 Roadmap

### Phase 2 (Networking)
- [ ] Интеграция OpenWeatherMap API
- [ ] Интеграция IQAir API для реальных AQI данных
- [ ] CoreLocation для определения текущей позиции

### Phase 3 (Features)
- [ ] Push notifications при высоком AQI
- [ ] SwiftData для истории локаций
- [ ] Widgets для Home Screen
- [ ] Apple Watch companion app

### Phase 4 (Polish)
- [ ] Animations и transitions
- [ ] Haptic feedback
- [ ] Localization (EN/RU/KZ)
- [ ] Dark/Light theme toggle

## 👨‍💻 Разработчик

Alexander Kisslitsyn  
Alikhan Amangeldiyev
Almaty, Kazakhstan 🇰🇿

---

**Версия**: 1.0 (Phase 1)  
**Дата**: Май 2026  
**License**: MIT
