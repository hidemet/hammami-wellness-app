# Hammami Hub

An Android application for wellness centers designed to streamline booking, reward loyal customers, and drive user engagement.

## The Problem & Vision

**The Problem:** Traditional wellness centers often rely on slow, manual booking processes (phone calls, paper agendas) and lack digital tools to foster customer retention. Customers want an immediate way to view availability, pay, and get rewarded for their loyalty without friction.

**The Solution:** Hammami Hub digitizes the entire customer journey. Targeting a broad demographic (ages 18-70), the app follows a strict *"walk-up-and-use"* design philosophy. By combining a frictionless booking system with an automated reward logic, it reduces the administrative burden on the staff and incentivizes customers to return and spend more flexibly.

## Product Development Lifecycle

This project was built following a strict Product Design and Software Engineering pipeline:

1. **User Research:** Conducted initial surveys and created *Personas* to understand the technical literacy and needs of both the customers (end-users) and the staff (secretaries, directors).
2. **Competitor Analysis:** Benchmarked existing wellness apps (e.g., Dahara, Centro Benessere Colle) to identify missing key features like integrated payments, reward points, and built-in reviews.
3. **Prototyping & Design:** Engineered an interactive mockup using **Figma**, fully adhering to **Material Design 3** guidelines and applying mobile design patterns to ensure an intuitive interface for low-tech individuals.
4. **Development:** Implementation of the complete native app in a native Android environment.

## Core Features

* **Real-time Catalog & Booking:** Browse services (Aesthetics, Wellness, Massages), view detailed descriptions, pricing, duration, and dynamically book available slots.
* **Reward System (Karma Points):** Users earn Karma Points based on their spending, which can be accumulated to redeem exclusive **Coupons** usable directly at checkout.
* **Gift Cards Engine:** Purchase and send digital Gift Cards natively within the app.
* **Digital Profile & Firebase Auth:** Seamless login, profile editing, and secure data synchronization via the cloud.
* **Review System:** Integrated system to leave feedback on completed appointments.

## Architecture & Tech Stack

The application has been engineered to meet modern enterprise-grade Android standards:

* **Language:** `Kotlin`
* **Architecture:** **MVVM (Model-View-ViewModel)** with **Clean Architecture** principles (Data, Domain, Presentation layers).
* **Dependency Injection:** `Dagger Hilt` for robust component scoping and modularity.
* **Backend as a Service:** `Google Firebase` 
  * *Firestore* (NoSQL Database for Treatments, Bookings, Users, Coupons)
  * *Authentication* (Secure login pipeline)
  * *Storage* (Media hosting)
* **Concurrency:** `Kotlin Coroutines`
* **UI Design:** `View/Data Binding` and `Material Design 3`
* **Error Handling:** Custom Result wrappers mapping domain logic over Firebase Exceptions.

## Information Architecture & Navigation Map

Before development, the entire navigation architecture was mapped out to ensure a logical and intuitive user experience. The following diagram illustrates the main navigation flows from a customer's perspective.

![App Navigation Map](media/navigation-map.png)

## UI & Design 
Here are the finalized UI screens designed with Material Design 3 guidelines:

**Home Dashboard**  
![Home Dashboard](media/home%20dashboard%20page.png)

**Services Catalog**  
![Services](media/services%20page.png)

**Service Detail**  
![Service Detail](media/service%20detail%20page.png)

**Booking Calendar**  
![Booking Calendar](media/booking-calendar%20page.png)

**Checkout / Payment**  
![Payment](media/payment%20page.png)

**Reward Coupons**  
![Coupon](media/coupon%20page.png)

## Assets & Documentation

Deep dive into the engineering and design process:

* **Interactive Mockup:** [View on Figma](https://www.figma.com/design/7mJzNG0WF3RerFoHGTPknW/Material-3-Design-Kit--Community-?node-id=55908-54774&t=YZoReQabeNy1w2rK-1)
* **Project Slides:** [slide-presentazione-hammami.pdf](./slide-presentazione-hammami.pdf)
* **Technical Report:** [relazione-hammami.pdf](./relazione-hammami.pdf)

---
*Created by Nicholas Dumas & Matteo Rossini*
