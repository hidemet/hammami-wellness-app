# Hammami Hub: Wellness Center Booking & Customer Loyalty Android App

[![Kotlin](https://img.shields.io/badge/Kotlin-Native%20Android-7F52FF.svg?style=flat&logo=kotlin&logoColor=white)](https://kotlinlang.org/)
[![Architecture](https://img.shields.io/badge/Architecture-Clean%20%2B%20MVVM-blue.svg?style=flat)]()
[![Firebase](https://img.shields.io/badge/Backend-Google%20Firebase-FFCA28.svg?style=flat&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![Material 3](https://img.shields.io/badge/UI-Material%20Design%203-green.svg?style=flat)]()
[![Dagger Hilt](https://img.shields.io/badge/DI-Dagger%20Hilt-orange.svg?style=flat)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat)](LICENSE)

> A production-ready native Android application engineered to digitize the entire booking and customer loyalty lifecycle for wellness centers, built on **Clean Architecture**, **MVVM**, and **Google Firebase**.

---

## 📖 Overview & Business Value

Traditional wellness and spa facilities often rely on manual, friction-heavy booking processes (phone calls, paper calendars) and lack automated customer retention tools.

**Hammami Hub** bridges this gap through a frictionless, *"walk-up-and-use"* mobile experience:
- **Instant Slot Booking:** Real-time visibility into treatments, staff availability, and immediate checkout.
- **Automated Retention Engine:** Customers earn **Karma Points** proportional to spending, which convert into redeemable coupons and digital gift cards directly at checkout.
- **Administrative Relief:** Real-time synchronization eliminates double-booking errors and reduces phone inquiries.

---

## 🏛️ System Architecture

The application is structured into distinct, modular layers following **Clean Architecture** to ensure testability and high cohesion:

```mermaid
graph TD
    subgraph UI ["Presentation Layer (MVVM & Material 3)"]
        Views["Activities & Fragments<br/>(ViewBinding, Material Design 3)"]
        VMs["ViewModels<br/>(Coroutines, StateFlow)"]
        Views -->|Observes State| VMs
    end

    subgraph Domain ["Domain Layer (Business Logic)"]
        UC1["BookTreatmentUseCase"]
        UC2["RedeemKarmaPointsUseCase"]
        UC3["ManageGiftCardsUseCase"]
        VMs --> UC1
        VMs --> UC2
        VMs --> UC3
    end

    subgraph Data ["Data Layer & Cloud Backend"]
        Repo["WellnessRepositoryImpl"]
        UC1 --> Repo
        UC2 --> Repo
        UC3 --> Repo
        
        subgraph Firebase ["Google Firebase Cloud Platform"]
            Firestore[("Cloud Firestore<br/>(NoSQL DB: Treatments, Bookings, Users, Coupons)")]
            Auth["Firebase Authentication<br/>(Secure Session Management)"]
            Storage["Firebase Storage<br/>(Media & Service Assets)"]
        end

        Repo --> Firestore
        Repo --> Auth
        Repo --> Storage
    end
```

---

## ✨ Core Features

1. **Live Services Catalog:** Filter treatments by category (Aesthetics, Massages, Holistic Care), with duration, pricing, and practitioner details.
2. **Dynamic Karma Points Loyalty System:** Automated point accrual per booking, redeemable for discount vouchers.
3. **In-App Digital Gift Cards:** Purchase, customize, and transfer electronic gift cards natively.
4. **Secure User Profile & History:** Access upcoming appointments, past treatment notes, and invoices.
5. **Verified Customer Feedback:** Transparent review engine after completed appointments.

---

## 📱 UI & Screen Showcase

| Home Dashboard | Services Catalog | Service Details |
| :---: | :---: | :---: |
| <img src="media/home%20dashboard%20page.png" width="260" alt="Home Dashboard" /> | <img src="media/services%20page.png" width="260" alt="Services Page" /> | <img src="media/service%20detail%20page.png" width="260" alt="Service Detail" /> |

### Navigation Architecture Map
<p align="center">
  <img src="media/navigation-map.png" width="750" alt="Application Navigation Flow" />
</p>

---

## 🛠️ Tech Stack

- **Language:** Kotlin
- **Architecture:** Clean Architecture (Data, Domain, Presentation) + MVVM
- **Dependency Injection:** Dagger Hilt
- **Backend as a Service:** Google Firebase (Cloud Firestore, Authentication, Cloud Storage)
- **Asynchrony:** Kotlin Coroutines
- **UI Framework:** Android ViewBinding, XML Layouts, Material Design 3
- **Error Handling:** Custom Result/Either sealed classes wrapping Firebase network exceptions

---

## 🚀 Setup & Local Execution

1. Clone the repository:
   ```bash
   git clone https://github.com/hidemet/hammami-wellness-app.git
   cd hammami-wellness-app
   ```
2. Open the project in **Android Studio**.
3. Place your `google-services.json` file inside the `app/` directory (or use the provided sandbox config).
4. Build and run on an Android emulator or device (Min SDK 26, Target SDK 34).

---

## 📄 License

Released under the [MIT License](LICENSE).
