# 🛡️ Cybersecurity Ecosystem — Yananth Fajardo

> **Framework modular diseñado para la simulación de operaciones SOC (Security Operations Center), integrando automatización de red, detección activa de intrusiones y análisis de eventos de seguridad.**

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![SOC Focus](https://img.shields.io/badge/Focus-Blue%20Team%20%7C%20SOC-blue?style=for-the-badge)
![Security+](https://img.shields.io/badge/Prep-CompTIA%20Security%2B-red?style=for-the-badge)

---

## ⚠️ Professional Disclaimer / Descargo de Responsabilidad

> [!IMPORTANT]
> **Uso Ético y Educativo:** Este ecosistema ha sido desarrollado exclusivamente con fines educativos, de investigación y para la simulación de entornos controlados (Laboratorios Blue Team). 
> 
> * **No para Producción:** No se recomienda el uso de estas herramientas en infraestructuras críticas sin una auditoría de seguridad previa.
> * **Responsabilidad:** El autor no se hace responsable del mal uso de estas herramientas. El acceso no autorizado a sistemas informáticos es ilegal y constituye un delito en la mayoría de las legislaciones internacionales.
> * **Ética Hacker:** "With great power comes great responsibility." Utiliza este conocimiento siempre bajo el marco de la legalidad y la ética profesional.

---

## 🧠 Arquitectura del Sistema (Mini SIEM)

El ecosistema utiliza una arquitectura orientada a eventos para procesar datos desde la infraestructura hasta el analista.

```mermaid
graph TD
    subgraph "Infraestructura & Gestión"
    A[🌐 Network Security Tool] -->|Push Config| B(Dispositivos de Red)
    B -->|Pull Backups| A
    end

    subgraph "Monitoreo & Detección"
    C[🚨 Sentinel Watch IDS] -->|Sniffing / PCAP| B
    C -->|Alertas de Tráfico| E{🛡️ Guardian Engine}
    B -->|Syslog / SNMP| E
    end

    subgraph "Capa de Inteligencia"
    E -->|Correlación| F[Analista de Seguridad]
    E -.->|Respuesta Automatizada| A
    end

    style E fill:#1f425f,stroke:#333,stroke-width:2px,color:#fff
    style A fill:#2e7d32,color:#fff
    style C fill:#c62828,color:#fff


