
# 🛡️ Mi Laboratorio de Ciberseguridad - eJPT

Este repositorio contiene los writeups detallados de las máquinas vulneradas durante mi preparación para la certificación **eJPT** (Junior Penetration Tester). Cada informe incluye la metodología completa: reconocimiento, explotación y escalada de privilegios.

## 🚀 Máquinas Resueltas

| Máquina | Dificultad | SO | Writeup |
| :--- | :--- | :--- | :--- |
| **Psycho** | Media | Linux | [Ver Writeup](./pyscho-writeup.md) |
| **Trust** | Muy Facil | Linux | [Ver Writeup](./trust-writeup.md)  |
| **Firsthacking** | Muy Facil | Linux | [Ver Writeup](./firsthacking-writeup.md)  |
---

## 🛠️ Metodología General

En cada reto sigo las fases estándar de un Pentesting:

1. [cite_start]**Reconocimiento**: Escaneo de puertos y servicios con `nmap`[cite: 7].
2. [cite_start]**Enumeración**: Fuzzing de directorios y parámetros (`gobuster`, `wfuzz`)[cite: 23, 57].
3. [cite_start]**Explotación**: Aprovechamiento de vulnerabilidades web (LFI) o servicios mal configurados[cite: 78, 83].
4. [cite_start]**Escalada de Privilegios**: Movimiento lateral y vertical hasta obtener acceso como `root`[cite: 121, 171].

## 💻 Herramientas Utilizadas
* [cite_start]**Nmap**: Análisis de red[cite: 7].
* [cite_start]**Wfuzz / Gobuster**: Enumeración web[cite: 24, 57].
* [cite_start]**Python / Perl**: Scripts para escalada de privilegios[cite: 121, 170].
* [cite_start]**SSH**: Acceso remoto mediante llaves privadas[cite: 92].

---
*Certificación en progreso: eJPT v2*
