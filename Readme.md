# IT/BWL Exam Master Sheet (DE + TR + EN)

Kompakte, druckfreundliche Zusammenfassung aus allen Notizen in `notes.txt`.  
Ziel: schnelle Wiederholung vor der Prüfung mit klaren Merksaetzen.
Englische Bedeutungen stehen in Klammern direkt neben Schluesselbegriffen.

---

## 1) Marktformen (Market Structures)

| Merkmal | Monopol | Oligopol | Polypol |
| --- | --- | --- | --- |
| Anbieter | 1 | wenige | viele |
| Nachfrager | viele | viele | viele |
| Preisbildung | Anbieter | gegenseitige Beeinflussung | Markt |
| Wettbewerb | keiner | mittel | hoch |
| Wahlfreiheit Kunde | gering | mittel | hoch |

- **Angebotsmonopol (Seller Monopoly):** ein Anbieter, viele Kunden (z. B. Stromanbieter)
- **Nachfragemonopol / Monopson (Buyer Monopoly / Monopsony):** ein Nachfrager, viele Anbieter (z. B. Staat als Einzelkaeufer)

**Merksatz:** Monopol = 1 Anbieter, Oligopol = wenige Anbieter, Polypol = viele Anbieter.

---

## 2) Backup & XCOPY

### Backup-Arten (Backup Types)

- **Differenziell (Differential Backup):** alle Aenderungen seit dem letzten Vollbackup
- **Inkrementell (Incremental Backup):** nur Aenderungen seit dem letzten Backup

### XCOPY (wichtig)

```bash
XCOPY Quelle Ziel /A /D:Datum /E /C /Y
```

- `/A` Archiv-Bit nicht aendern  
- `/D` nach Datum  
- `/E` alle Ordner inkl. leer  
- `/C` bei Fehlern weitermachen  
- `/Y` ohne Rueckfrage ueberschreiben

---

## 3) Networking Basics

### IP-Adressen (IP Addresses, Pruefungsklassiker)

| Adresse | Bedeutung |
| --- | --- |
| `127.0.0.1` | Loopback (eigener PC) |
| `169.254.x.x` | APIPA (DHCP fehlt) |
| `0.0.0.0` | Unspecified (noch keine IP) |

### APIPA (Automatic Private IP Addressing)

- APIPA entsteht, wenn ein Geraet keine Antwort vom DHCP-Server bekommt
- Bereich (range): `169.254.0.0` bis `169.254.255.255`
- Bedeutung: Geraet vergibt sich selbst eine lokale IP
- Einschraenkung: meist **kein Internet**, nur lokales Netzwerk
- Pruefung unter Windows: `ipconfig` -> `169.254.x.x` zeigt DHCP-Problem

### Router, NAT, Firewall

- **DHCP (Dynamic Host Configuration Protocol):** automatische IP-Vergabe
- **NAT (Network Address Translation):** private IP -> oeffentliche IP
- **Firewall:** Datenverkehr erlauben/blockieren (allow/block traffic)

**Merksatz:** NAT wandelt um, Firewall kontrolliert.

---

## 4) OSI-Modell (OSI Model, 7 -> 1)

**Reihenfolge-Mnemonic:** *Please Do Not Throw Sausage Pizza Away*

1. Anwendung (Application Layer) - HTTP/HTTPS  
2. Darstellung (Presentation Layer) - SSL/TLS  
3. Sitzung (Session Layer) - NetBIOS/RPC  
4. Transport (Transport Layer) - TCP/UDP (**Segment**)  
5. Vermittlung/Network (Network Layer) - IP (**Packet**)  
6. Sicherung/Data Link (Data Link Layer) - Ethernet (**Frame**)  
7. Bituebertragung/Physical (Physical Layer) (**Bit**)

### Datenfluss-Mnemonic

**Data -> Segment -> Packet -> Frame -> Bit**  
(*Do Some People Feel Bad*)

### Typische Geraete

- Layer 3: Router, Layer-3-Switch  
- Layer 2: Switch, Bridge  
- Layer 1: Kabel, Hub, Repeater

### OSI Schnell-Tabelle (EN/DE + Beispiele)

| Layer | Name (EN / DE) | Data Name | Protokolle (Beispiele) | Typische Geraete |
| --- | --- | --- | --- | --- |
| 7 | Application / Anwendung | Data | HTTP, FTP, SMTP, DNS | PC, Browser |
| 6 | Presentation / Darstellung | Data | SSL/TLS, JPEG, MP3 | PC |
| 5 | Session / Sitzung | Data | NetBIOS, RPC | PC |
| 4 | Transport / Transport | Segment | TCP, UDP | PC |
| 3 | Network / Vermittlung | Packet | IP, ICMP | Router |
| 2 | Data Link / Sicherung | Frame | Ethernet, MAC | Switch |
| 1 | Physical / Bituebertragung | Bit | elektrische Signale | Kabel, Hub |

**RPC (Remote Procedure Call):** Eine Funktion auf einem anderen Rechner so aufrufen, als waere sie lokal.

---

## 5) IT-Sicherheit, Datenschutz, ISMS (Security & Privacy)

### Grundbegriffe

- **Verschluesselung (Encryption):** Daten unlesbar fuer Unbefugte
- **Authentifizierung (Authentication):** Wer bist du? (Login)
- **Autorisierung (Authorization):** Was darfst du? (Rechte)

### Datenschutz vs Datensicherheit

- **Datenschutz (Data Privacy):** Schutz personenbezogener Daten (DSGVO)
- **Datensicherheit (Data Security):** Schutz vor Verlust, Manipulation, Angriff

### Zugang vs Zugriff

- **Zugangskontrolle (Access Admission Control):** Wer darf sich anmelden?
- **Zugriffskontrolle (Access Rights Control):** Auf welche Daten/Funktionen darf man zugreifen?

### Schutzziele (BSI/CIA + A)

1. Vertraulichkeit (Confidentiality)  
2. Integritaet (Integrity)  
3. Verfuegbarkeit (Availability)  
4. Authentizitaet (Authenticity)

### ISMS

- **ISMS = Information Security Management System**
- Schuetzt Informationen systematisch im Unternehmen
- Kernziele: Vertraulichkeit, Integritaet, Verfuegbarkeit

### Security Awareness

- Regelmaessige Schulungen
- Phishing-Simulationen
- Sicherheitsrichtlinien und Kampagnen

### CIA Triad + Mechanismen

- **C - Vertraulichkeit (Confidentiality):** Wer darf Daten sehen?
- **I - Integritaet (Integrity):** Sind Daten korrekt/unveraendert?
- **A - Verfuegbarkeit (Availability):** Ist System/Dienst nutzbar?

**Security Mechanisms (Schutzmechanismen):**
- **Encryption (Verschluesselung):** Daten unlesbar machen
- **Authentication (Authentifizierung):** Identitaet pruefen (wer bist du?)
- **Authorization (Autorisierung):** Rechte vergeben (was darfst du?)

---

## 6) Passwortsicherheit & Hardening (Password Security & System Hardening)

### Gute Passwortregeln

- Gross-/Kleinbuchstaben, Zahlen, Sonderzeichen
- Keine einfachen Woerter
- Nicht wiederverwenden
- Regelmaessig aendern
- Sperrmechanismen bei Fehlversuchen

### Warum Passwortwechsel?

- Gestohlene Passwoerter werden unbrauchbar
- Risiko fuer unbefugten Zugriff sinkt

### Hardening

- Unnoetige Dienste deaktivieren
- Updates/Patches installieren
- Standardpasswoerter aendern
- Firewall aktivieren

---

## 7) Cloud Computing

### Servicemodelle (Service Models)

- **SaaS (Software as a Service):** fertige Software nutzen (z. B. Gmail, Office 365)
- **PaaS (Platform as a Service):** Plattform zum Entwickeln/Deployen eigener Software

### Bereitstellungsmodelle (Deployment Models)

- **Public Cloud:** viele Nutzer, geteilte Ressourcen, weniger Kontrolle
- **Private Cloud:** nur ein Unternehmen, mehr Kontrolle/Sicherheit
- **Hybrid Cloud:** Mischung aus Public + Private

### Cloud-Vorteile

- keine eigene Server-Hardware
- geringere Wartungskosten
- bessere Skalierbarkeit
- oft geringerer Personalaufwand

### Cloud vs Webhosting

- **Cloud:** mehrere Server, flexibel skalierbar
- **Webhosting:** meist einzelner Server, begrenzter

---

## 8) IT-Infrastruktur, Virtualisierung, USV (Infrastructure, Virtualization, UPS)

### Zentral vs Dezentral

- **Zentral:** einfache Verwaltung, geringe Kosten
- **Dezentral:** flexibel, ausfallsicher

### Virtualisierung

- Ein physischer Server betreibt mehrere virtuelle Systeme
- Vorteile: Kosten senken, Auslastung verbessern
- Nachteil: Host-Ausfall trifft viele Systeme

### USV (Uninterruptible Power Supply, UPS)

- liefert Strom bei Ausfall
- verhindert Datenverlust und abruptes Herunterfahren

---

## 9) Systeme & Unternehmenssoftware (Enterprise Systems)

### DMS vs CMS

- **DMS (Dokumentenmanagementsystem / Document Management System):** Dokumente verwalten (PDF, Rechnung, Vertrag)
- **CMS (Content-Management-System / Content Management System):** Website-Inhalte verwalten (Texte, Bilder, Seiten)

### CRM vs ERP

- **CRM (Customer Relationship Management):** Kundendaten/Kontakte verwalten, Kundenbetreuung verbessern
- **ERP (Enterprise Resource Planning):** Ressourcen und Unternehmensprozesse planen (Einkauf, Lager, Finanzen)

### Library vs Framework

- **Library:** dein Code ruft die Bibliothek auf
- **Framework:** das Framework ruft deinen Code auf

### Lastenheft vs Pflichtenheft

- **Lastenheft (Requirements Specification):** WAS der Kunde will
- **Pflichtenheft (Functional/Technical Specification):** WIE die Firma es umsetzt

---

## 10) Projektmanagement (Project Management)

### Netzplan (Network Diagram / Project Schedule)

- `FAZ + Dauer = FEZ`
- `SAZ - FAZ = Puffer`
- **Kritischer Weg:** kein Puffer

### Stakeholder

- Personen/Gruppen mit Interesse am Projekt
- Analyse oft ueber Matrix: Einfluss (Macht) x Einstellung

### Rahmenbedingungen

- Zeit (Termin)
- Kosten (Budget)
- Recht (Gesetze)

### Vor-/Nachkalkulation

- **Vorkalkulation:** erwartete Kosten (Personal, Material)
- **Nachkalkulation:** Ist-Kosten pruefen, Fehler erkennen, verbessern

### Kennzahl & Sollwert (KPI & Target Value)

- **Kennzahl (KPI / Metric):** messbarer Ist-Zustand
- **Sollwert (Target Value):** Zielwert

---

## 11) IT Support & Fehlermanagement (Incident/Error Management)

### Support-Level

- **1st-Level:** einfache Probleme, Ticketaufnahme, Weiterleitung
- **2nd-Level:** tiefere Analyse und Loesung
- **3rd-Level:** Experten/Entwickler fuer komplexe Faelle

### Ticketsystem

- Stoerungen erfassen/speichern
- Tickets zuweisen
- Bearbeitung und Loesung dokumentieren

### Datenerhebung (Support-Optimierung)

- Beobachtung
- Interview
- Dokumentenanalyse (Tickets/Berichte)

### Fehlermanagement-Phasen (Error Management Phases)

1. Fehlerentdeckung  
2. Fehlerdiagnose  
3. Fehlerloesung/-korrektur

### Schulungsmethoden

- Webinar (online)
- Multiplikatoren-Schulung (Train-the-Trainer)

### Malware-Arten

- Virus, Wurm, Trojaner, Ransomware, Spyware, Adware

---

## 12) Hardware & Arbeitsplatz (Hardware & Workplace)

### Notebook vs Desktop

**Notebook Vorteile:** mobil, platzsparend, geringerer Stromverbrauch  
**Notebook Nachteile:** geringere Leistung, schwieriger Upgrade/Reparatur, kleinerer Bildschirm

### Tablet (Nachteile)

- geringere Leistung
- schwierigere Eingabe
- eingeschraenkte Softwareauswahl

### Dockingstation

- Notebook schnell mit Monitor, Tastatur, Maus verbinden
- macht stationaeres Arbeiten komfortabler

### Thin Client

- arbeitet serverbasiert mit geringer lokaler Leistung
- Vorteile: zentrale Verwaltung, geringere Kosten/Strom

### All-in-One PC

- alles in einem Gehaeuse
- Nachteil: schwerer aufzuruesten, Reparaturen oft teuer

### Speicher & Komponenten (Storage & Components)

- **SSD:** schneller/robuster, aber teurer pro GB
- **HDD:** guenstiger, aber langsamer
- **RAM ECC (Error-Correcting Code):** erkennt/korrigiert Speicherfehler
- **DDR5:** schneller als DDR4

### Dateisysteme

- FAT32 (kompatibel, oft USB)
- NTFS (Windows)
- APFS (Apple)
- EXT4 (Linux)

### Anschluesse

- USB-C, HDMI, DisplayPort

### Barrierefreier Arbeitsplatz (Accessible Workplace)

- Spezialtastatur, Trackball/spezielle Maus
- grosser Monitor, Headset

---

## 13) OOP, Debugging, Algorithmus (Object-Oriented Programming)

### OOP Basics

- **Klasse (Class):** Bauplan
- **Objekt (Object):** Instanz
- **Methode (Method):** Verhalten/Funktion der Klasse

### Vererbung (Inheritance, Ticket-Beispiel)

- Oberklasse: gemeinsame Attribute/Methoden
- Unterklasse: spezialisierte Attribute/Methoden
- gleiche Methodennamen in Unterklassen -> Polymorphismus (polymorphism)

### Debugging

- Breakpoints setzen
- Step Over / Step Into
- Variablen beobachten
- optional: Call Stack, Logging

### Primzahl-Algorithmus (kurz)

1. `n <= 1` -> false  
2. pruefe Teiler von `2` bis `sqrt(n)`  
3. wenn teilbar -> false  
4. sonst -> true

---

## 14) Elektrotechnik Grundlagen (Electrical Fundamentals)

### Begriffe

- **Spannung (U/V, Voltage):** Energie pro Ladung
- **Strom (I/A, Current):** Ladung pro Zeit
- **Widerstand (R, Resistance):** Hemmung des Stroms
- **Leistung (P/W, Power):** Arbeit pro Zeit
- **Ladung (Q, Charge):** Menge elektrischer Ladung

### Wichtige Formeln

- `U = I * R`
- `I = Q / t`
- `P = U * I`
- `P = I^2 * R`
- `E = Q * U`
- `eta = P_nutz / P_zu`

### Sicherheitslogik

- Strom ist fuer den Koerper gefaehrlich (mA-Bereich relevant)
- Kurzschluss: `R ~ 0` -> sehr grosser Strom
- Spannung ist Ursache, Strom ist Wirkung

### Merkbilder

- Wasservergleich: Spannung = Druck, Strom = Wassermenge, Widerstand = Engstelle

---

## 15) BWL Kurzthemen (Business Basics)

### Darlehen (Abzahlungsdarlehen / Amortizing Loan)

- Tilgung meist konstant
- Zinsen auf Restschuld
- Rate = Tilgung + Zinsen

### Prozentrechnung

- `(Differenz / Referenz) * 100`
- Referenz ist oft der guenstigere Ausgangswert

### Urheberrecht (Copyright Basics)

- Schutz typischerweise bis 70 Jahre nach Tod des Urhebers
- umfasst u. a. Namensnennung/Nutzungsrechte

### Angebot

- **Inhaltlich (Content-related):** Preis, Leistung, Produktbeschreibung
- **Formal (Formal requirements):** Datum, Adresse, Unterschrift

### Vertrieb

- **Direkt (Direct Sales):** ohne Zwischenhaendler
- **Indirekt (Indirect Sales):** mit Zwischenhaendler

### Organisationsformen (Organizational Structures, DE + EN)

| Organisationsform (EN) | Eigenschaften (Characteristics) | Vorteile (Advantages) | Nachteile (Disadvantages) |
| --- | --- | --- | --- |
| **Linienorganisation** (Line organization) | Ein Vorgesetzter; klare Hierarchie; feste Zustaendigkeiten | Einfache Struktur; klare Verantwortung; schnelle Entscheidungen | Wenig flexibel; Ueberlastung der Fuehrung; geringe Innovation |
| **Stablinienorganisation** (Line-and-staff) | Linie + Stab (Beratung); Stab hat **keine Weisungsbefugnis** (no command authority); Unterstuetzung der Leitung | Nutzung von Expertenwissen; bessere Entscheidungen; Entlastung der Fuehrung | Hoeherer Kommunikationsaufwand; Konfliktpotenzial; hoehere Kosten |
| **Spartenorganisation** (Divisional / product-based) | Gliederung nach Produkten/Maerkten; Sparten relativ eigenstaendig; eigene Leitung je Sparte | Marktorientiert; hohe Flexibilitaet; schnelle Reaktion | Doppelte Ressourcen; hoher Koordinationsaufwand; hohe Kosten |
| **Matrixorganisation** (Matrix) | Mehrere Vorgesetzte; Kombination Funktion + Produkt; teamorientiert | Bessere Zusammenarbeit; hohe Flexibilitaet; Nutzung von Fachwissen | Konflikte moeglich; unklare Zustaendigkeiten; hoher Abstimmungsaufwand |

**Merksatz Stab:** Stab **beraet**, Linie **entscheidet** (Staff advises; line decides).

---

## 16) ER-Modell (ER Model, Pruefung)

### Beispielstruktur

- `Mitarbeiter(Mitarbeiternummer PK, Login)`
- `Projekt(Projekttitel PK, Budget, Zieltermin, Mitarbeiternummer FK)`

### Beziehung

- Mitarbeiter `(1)` leitet Projekt `(n)`
- Fremdschluessel (Foreign Key) auf die **n-Seite**

**Merksatz:** Login ist Attribut, kein eigenes Entity.

---

## 17) Typische Pruefungsfallen (Common Exam Traps)

- Bei Formulierungen wie **"neben ..."**: den genannten Punkt nicht wiederholen
- Bei **Mitarbeiter-Bewusstsein**: Schulung/Awareness ist oft richtige Richtung
- Bei **BSI/Schutzbedarf**: an CIA + A denken
- Bei **1:n Beziehungen**: FK auf n-Seite
- Bei **Passwoertern**: Komplexitaet und Wiederverwendung beachten

---

## 18) Ultra-Merksaetze (1 Minute vor Pruefung)

- `169.254.x.x` = DHCP fehlt (APIPA)
- `0.0.0.0` = noch keine IP
- Differenziell = seit Vollbackup
- Inkrementell = seit letztem Backup
- Library = du rufst; Framework = du wirst gerufen
- Lastenheft = WAS; Pflichtenheft = WIE
- CRM = Kunden; ERP = Ressourcen/Prozesse
- DMS = Dokumente; CMS = Website-Inhalte
- NAT = Uebersetzung; Firewall = Kontrolle
- Schutzbedarf = Vertraulichkeit, Integritaet, Verfuegbarkeit, Authentizitaet

---

## Druckhinweis

Fuer Ausdruck in A4:

- in Markdown-Preview drucken (Browser/Editor)
- Skalierung auf **90-95%**
- Kopf-/Fusszeilen deaktivieren fuer sauberes Layout

