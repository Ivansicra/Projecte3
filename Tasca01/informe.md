# CFGM Sistemes Microinformàtics i Xarxes  
## T05: Anàlisi de l’entorn  
### Possibles models de negoci pels clients tecnològics de la consultoria — FASE 1

**Autor:** Ivan Sicra  
**Data:** 21/10/25  

**Accés al document original:**  
[Google Docs](https://docs.google.com/document/d/1R_ubzeeFja08ZBLEnqp4HdciZhEUcZ8XXlhzQ3QGAu8/edit?usp=sharing)

---

## 📚 Índex
- [Introducció](#introducció)
- [Alternatives](#alternatives)
- [Comparativa](#comparativa)
- [Avantatges](#avantatges)
- [Inconvenients](#inconvenients)
- [Recomanació final](#recomanació-final)

---

## 🧩 Introducció
En l’actual entorn digital, la seguretat de les credencials d’accés és un pilar fonamental per a la protecció dels sistemes corporatius.  
Les contrasenyes febles, reutilitzades o mal gestionades són una porta d’entrada habitual per a ciberatacs.  

Amenaces com els **atacs de diccionari**, el **credential stuffing** o el **phishing** aprofiten patrons previsibles i credencials filtrades per accedir il·legalment a sistemes interns.  

Aquest tipus d’incidents poden derivar en:
- Pèrdues econòmiques  
- Compromís de dades sensibles  
- Danys reputacionals  

Davant d’aquest escenari, la Direcció considera imprescindible **adoptar una eina que permeti gestionar les contrasenyes de forma segura i eficient.**

---

## 🔍 Alternatives Analitzades

### **Bitwarden (Model Online / Núvol)**
![Captura 1](img/logo.png)

- **Sincronització:** Automàtica entre dispositius via núvol  
- **Seguretat:** Xifratge end-to-end amb AES-256 i derivació de claus PBKDF2-SHA-256  
- **Accessibilitat:** Compatible amb navegadors, mòbils i escriptori  
- **Model de cost:** Freemium, amb versió gratuïta funcional i opcions premium  
- **Open Source:** Codi disponible públicament  

---

### **KeePassXC (Model Offline / Escriptori)**
![KeePassXC logo](https://raw.githubusercontent.com/tu-usuari/tu-repo/main/img/keepassxc.png)

- **Emmagatzematge:** Local mitjançant arxiu KDBX  
- **Seguretat:** Xifratge amb AES-256, ChaCha20 o Twofish  
- **Accessibilitat:** Compatible amb Windows, macOS i Linux; no té aplicació mòbil nativa  
- **Model de cost:** Totalment gratuït  
- **Open Source:** Desenvolupament comunitari i transparent  

---

## 📊 Anàlisi Comparativa

| Aspecte | Bitwarden | KeePassXC |
|----------|------------|-----------|
| **Sincronització** | Automàtica via núvol | Manual (USB, Nextcloud, etc.) |
| **Accés multidispositiu** | Navegador, mòbil, escriptori | Només escriptori |
| **Dependència d’internet** | Sí | No |
| **Control de dades** | Servidors xifrats de Bitwarden | Totalment local |
| **Facilitat d’ús** | Alta | Mitjana |
| **Escalabilitat** | Alta (compartició, equips) | Limitada |

---

## ⚙️ Avantatges i Inconvenients

### **Bitwarden**
✅ Comoditat i sincronització automàtica  
✅ Escalabilitat i entorns col·laboratius  
⚠️ Dependència del núvol  
⚠️ Necessitat de protegir l’accés principal amb autenticació robusta  

### **KeePassXC**
✅ Control total de les dades  
✅ Major resistència a atacs remots  
⚠️ Gestió manual de fitxers  
⚠️ Sense sincronització automàtica  

---

## 🧭 Recomanació Final
Tenint en compte les necessitats del personal tècnic, que sovint treballa amb múltiples dispositius i requereix accés ràpid i segur a credencials compartides, **es recomana la implementació de Bitwarden com a gestor corporatiu.**

Aquesta decisió es basa en:
- La seva capacitat de **sincronització entre plataformes**  
- La **robustesa del model de seguretat**  
- La **facilitat d’ús i integració** amb fluxos de treball moderns  
- La seva **escalabilitat** per a equips tècnics  

---

> 📄 *Document elaborat com a part del mòdul d’Anàlisi de l’entorn (FASE 1) – CFGM Sistemes Microinformàtics i Xarxes.*

