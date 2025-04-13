# 🧱 Minecraft Java Server unter Windows

Willkommen! Diese Anleitung zeigt dir Schritt für Schritt, wie du unter **Windows** einen Minecraft Java Server einrichtest – inklusive Java-Installation, Server-Download, Portfreigabe und Startskript. Ideal für Freunde, LAN-Partys oder deinen eigenen Online-Server.

---

## 📦 Voraussetzungen

- Windows 10 oder 11
- Java 17 oder neuer
- Eine stabile Internetverbindung
- Zugriff auf deinen Router zur Portfreigabe
- Optional: `start.bat`-Datei für einfaches Starten

---

## 🔧 Java 17 installieren

1. Lade das JDK von der offiziellen Seite herunter:  
   👉 [Java 17 von Oracle](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)

2. Wähle dein System (Windows x64 Installer) und installiere es.

3. Starte danach die Eingabeaufforderung (`Win + R` → `cmd`) und prüfe:
```cmd
java -version
```

Du solltest sowas sehen wie:
```
java version "17.x.x"
```

---

## 📂 Minecraft Server einrichten

1. Erstelle einen neuen Ordner, z. B. `C:\MinecraftServer`
2. Lade den Server herunter – empfohlen ist **Paper** für bessere Leistung:

👉 [https://papermc.io/downloads](https://papermc.io/downloads)

Wähle Version `1.20.4` oder aktueller → "Download"  
Benenne die heruntergeladene `.jar` Datei in `server.jar` um  
Speichere sie in deinen neuen Ordner.

---

## ▶️ Startskript erstellen

1. Öffne den Ordner `C:\MinecraftServer`
2. Erstelle eine neue Textdatei und nenne sie: `start.bat`
3. Rechtsklick → Bearbeiten und folgendes einfügen:

```bat
@echo off
java -Xmx2G -Xms1G -jar server.jar nogui
pause
```

💡 Du kannst `2G` anpassen, je nachdem wie viel RAM du geben willst.

4. Speichern und schließen

---

## 🚀 Server das erste Mal starten

Doppelklicke auf `start.bat`

Der Server startet kurz und beendet sich direkt – Grund: Du musst der EULA zustimmen.

### EULA akzeptieren

1. Öffne die Datei `eula.txt`
2. Ändere:
```
eula=false
```
zu:
```
eula=true
```

3. Speichern und nochmal `start.bat` doppelklicken

---

## 🌐 Portfreigabe im Router

Damit andere Spieler über das Internet beitreten können:

1. Öffne deinen Router im Browser (z. B. `http://fritz.box`)
2. Gehe zu **Portfreigaben** oder **NAT / Portweiterleitung**
3. Erstelle eine neue Freigabe:

   - **Port extern**: 25565  
   - **Port intern**: 25565  
   - **Protokoll**: TCP (ggf. auch UDP)  
   - **Ziel-IP**: lokale IP deines Rechners (z. B. 192.168.178.45)

4. Speichern und ggf. Router neustarten

### Eigene IP-Adresse herausfinden

Drücke `Win + R`, tippe `cmd`, dann:
```cmd
ipconfig
```

Suche nach deiner lokalen IPv4-Adresse, z. B. `192.168.178.45`

### Öffentliche IP anzeigen

🔗 [https://www.wieistmeineip.de](https://www.wieistmeineip.de)

---

## ⚙️ Server konfigurieren

Öffne `server.properties` mit dem Editor, um z. B. Folgendes zu ändern:

```properties
motd=Mein Minecraft Server
gamemode=survival
difficulty=normal
max-players=10
white-list=true
online-mode=true
```

Speichern → Server neu starten

---

## 🔗 Nützliche Links

| Beschreibung                 | Link |
|-----------------------------|------|
| Java 17 (Oracle Archiv)     | https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html |
| Minecraft Server (Vanilla)  | https://www.minecraft.net/de-de/download/server |
| PaperMC Server              | https://papermc.io/downloads |
| Öffentliche IP anzeigen     | https://www.wieistmeineip.de |
| Fritzbox Oberfläche         | http://fritz.box |

---

## ✅ Fertig!

Dein Server läuft jetzt unter Windows! 🎉 Freunde können über deine öffentliche IP auf Port `25565` beitreten. Beispiel:

```text
123.45.67.89:25565
```

---

## 📜 Zusammenfassung des Startskripts

```bat
@echo off
java -Xmx2G -Xms1G -jar server.jar nogui
pause
```

RAM-Zuweisung kannst du nach Wunsch erhöhen, z. B. `-Xmx4G`

---

## 🧠 Tipps

- Paper läuft schneller und stabiler als der Vanilla-Server
- Immer Backups machen, bevor du Änderungen machst
- Admins legst du in der Datei `ops.json` fest
- Nur bestimmte Spieler erlauben? Nutze `white-list=true`

---

## ☕ Viel Spaß beim Zocken!

Wenn dir dieses Projekt hilft, gib ihm gerne einen ⭐ auf GitHub 😊
