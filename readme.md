[README.md](https://github.com/user-attachments/files/31283110/README.md)

# 🎬 Anime Domain + (Android Native)

![Android](https://img.shields.io/badge/Android-Native_Kotlin-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9.22-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![ExoPlayer](https://img.shields.io/badge/Media3-ExoPlayer-FF4081?style=for-the-badge&logo=youtube&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-RTDB_%26_FCM-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)

**Anime Domain +** es una aplicación nativa de streaming de anime para Android estilo Netflix / Rave, construida completamente en **Kotlin puro**. Cuenta con un motor de scrapers nativos de alto rendimiento, sistema de salas de reproducción síncrona en vivo (**WatchParty**), actualizaciones Over-The-Air (**OTA**) in-app y una interfaz con acentos dinámicos personalizables remotamente.

---

## 🌟 Características Principales

### 📱 Experiencia de Usuario & Interfaz Premium
- **Diseño Glassmorphic Dinámico**: Gradientes globales adaptativos que reaccionan al color dominante de la portada del anime o configuración remota.
- **Navegación Fluida**: Barra inferior flotante con acceso rápido a Inicio, Buscador, Guardados, WatchParty y Perfil.
- **Paginación Inteligente**: Carga progresiva de catálogos ("Paginación por demanda") para ahorro de datos y fluidez.

### 👥 WatchParty en Tiempo Real
- **Salas Sincronizadas**: Ve episodios simultáneamente con amigos con control de sincronización de estado (`Play`, `Pause`, `Seek`).
- **Chat Interactivo**: Mensajería en vivo dentro de la sala con burbujas personalizadas, avisos de presencia y menciones.
- **Gestión de Espectadores**: Diálogo flotante para visualizar usuarios conectados, otorgar/cambiar anfitrión o expulsar espectadores (`Kick`).

### 🔄 Sistema de Actualizaciones OTA (In-App)
- **Descargas Autónomas**: Descarga e instala APKs de actualización directamente desde GitHub Releases sin necesidad de navegador.
- **Barra de Progreso en Tiempo Real**: Reporte de porcentaje y megabytes descargados.
- **Control Flexible**: Soporte para actualizaciones obligatorias (forzosas) u opcionales con opción de descarga manual.

### ⚡ Scrapers Nativos en Kotlin
- **Rendimiento Puro**: Extracción nativa con Jsoup y OkHttp que reemplaza esqueletos ciegos en JSON.
- **Soporte Multi-Servidor**: Extracción y descifrado de enlaces seguros (`UPNShare / uns.bio`, `MP4Upload`, `Mega`, `Zilla`, etc.).

---

## 🛠️ Arquitectura Técnica

```text
SplashActivity (Carga Gist RemoteConfig + Verificación OTA)
  ├── RemoteConfigManager (Flags remoto, colores dinámicos, providers)
  └── MainActivity (Navegación principal por Fragments)
       ├── HomeFragment (Hero carrusel, episodios recientes, categorización)
       ├── SearchFragment (Buscador unificado en tiempo real)
       ├── SavedFragment (Favoritos e historial local Room)
       ├── WatchPartyLobbyFragment (Creación y unirse a salas)
       └── ProfileFragment (Ajustes de audio, PiP, animaciones y perfil)
```

- **Lógica de Datos**: Room Database (`AppDatabase`) + Shared Preferences.
- **Reproductor**: Jetpack Media3 (ExoPlayer) con overlay customizado, gestos táctiles e integración PiP (Picture-in-Picture).
- **Control Remoto (Gist)**: Estado de servidores, mantenimiento, banners promocionales y control de scrapers.

---

## 📦 Repositorio de Releases & Descargas

Para descargar el APK de producción más reciente o verificar las notas de la versión:

👉 **[AnimeDomainPlusRelease en GitHub](https://github.com/darking101/AnimeDomainPlusRelease)**

---

## 📄 Licencia & Nota Privada

Este proyecto se desarrolló exclusivamente para fines educativos y de investigación sobre arquitecturas nativas en Android y protocolos de sincronización multimedia en tiempo real.
