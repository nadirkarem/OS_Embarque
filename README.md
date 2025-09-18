marp: true
theme: default
class: lead
paginate: true
---

# Problème 1 – APP1
## OS embarqué sur smartphone ARM

---

# Contexte
- Ancien smartphone Android (ARM)
- Disque remplacé → **vierge**
- Objectif : faire tourner une appli C
- Capteurs utilisés : **microphone**, **LED**

---

# Question 1 : Installation – Étapes
1. Choisir un système de base (Android, Linux embarqué, RTOS)
2. Préparer la **toolchain ARM** (cross-compilation)
3. Installer un **bootloader** (ex: U-Boot)
4. Flasher le système (fastboot, JTAG…)
5. Déployer l’application compilée

---

# Question 2 : Infrastructures possibles

### Option A – Android (AOSP + NDK)
- Réinstaller Android minimal
- Compiler en C avec le **NDK**
- Accès aux capteurs via API Android

---

### Option B – Linux embarqué
- Construire un Linux ARM (Yocto, Buildroot)
- Cross-compiler l’application
- Accès direct aux périphériques (GPIO, drivers)

---

### Option C – RTOS (FreeRTOS, Zephyr)
- Installer un RTOS léger
- Code C directement sur le noyau
- Très réactif, mais peu de services système

---

# Comparaison rapide

| Option            | Type d’OS     | Avantage principal | Limite principale |
|-------------------|--------------|-------------------|------------------|
| **Android**       | OS complet   | API capteurs      | Lourd, Java nécessaire |
| **Linux embarqué**| OS minimal   | Flexibilité, pur C| Configuration complexe |
| **RTOS**          | Temps réel   | Léger, rapide     | Pas d’API avancée |

---

# Conclusion provisoire
- Plusieurs solutions existent selon l’usage :
  - Android → API et capteurs
  - Linux → contrôle total en C
  - RTOS → léger et temps réel
- Étapes clés : **choisir l’OS + cross-compiler + flasher + tester**

