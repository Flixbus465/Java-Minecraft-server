Minecraft Java Server erstellen (Vanilla / Paper)
✅ Voraussetzungen:

PC mit Windows/Linux/Mac (am besten 24/7 an)
Installiertes Java (empfohlen: Java 17 oder höher)
Stabile Internetverbindung
Zugriff auf den Router (für Portfreigabe)
Minecraft Java Edition

🔧 Schritt 1: Java installieren
Besuche: https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html

Lade Java 17 (oder neuer) herunter und installiere es.
Überprüfe mit:

bash
java -version

📂 Schritt 2: Server-Dateien herunterladen
Vanilla:
Gehe auf https://www.minecraft.net/de-de/download/server
Lade server.jar herunter.

ODER

Paper (leistungsstärker):
Gehe auf https://papermc.io/downloads
Lade die neueste .jar herunter.

Erstelle auf deinem PC einen Ordner, z. B. MinecraftServer

Lege die .jar in diesen Ordner

🚀 Schritt 3: Server starten
Öffne ein Terminal (CMD oder Bash) im Ordner.

Starte mit:

bash:
java -Xmx2G -Xms1G -jar server.jar nogui
(Passe Xmx = max RAM, Xms = min RAM)

Es erscheint eula.txt. Öffne es und ändere:

txt:
eula=false
zu
txt:
eula=true
Starte den Server erneut mit dem gleichen Befehl.

🌐 Schritt 4: Portfreigabe (Router-Einstellungen)
Damit andere über das Internet joinen können:

Öffne deinen Router (Browser):
z. B. http://192.168.178.1 (Fritzbox), http://192.168.1.1 usw.

Logge dich ein (meist „admin“ und Passwort).
Gehe zu Portfreigabe oder NAT/Port-Forwarding
Erstelle eine neue Freigabe:

Protokoll: TCP (oder TCP + UDP)
Port extern & intern: 25565
Zielgerät: Dein PC / IP-Adresse (z. B. 192.168.178.25)
Name: „Minecraft Server“
Speichern

🌍 Schritt 5: Öffentlich joinen
Gib anderen deine öffentliche IP-Adresse:
Siehe https://www.wieistmeineip.de

Spieler verbinden mit:

text
DEINE-IP:25565

text
192.168.x.x:25565

🛡️ Empfehlung: Firewall erlauben
Falls andere nicht joinen können:

Öffne die Windows Firewall (oder deine Linux-Firewall)
Erlaube eingehende Verbindungen für java.exe bzw. den Port 25565

🧠 Optional: Server anpassen
In der Datei server.properties kannst du alles konfigurieren:

z. B. motd, gamemode, difficulty, pvp, max-players, white-list etc.
