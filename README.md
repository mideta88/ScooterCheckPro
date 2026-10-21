# ScooterCheck Pro G30D – 1.2 Beta

Kostenloser Prototyp für iPhone/Bluefy über HTTPS. Nicht behördlich validiert.

**Entwicklerangabe (vom Auftraggeber vorgegeben):** Polizei Bochum Direktion V VDG1 Denter RBr. Die Angabe stellt keine unabhängig geprüfte offizielle Herausgeberschaft oder behördliche Freigabe dar.

## Funktionen
- GATT-Geräteauswahl über Web Bluetooth; passive GATT-Discovery und ausschließlich readValue()/startNotifications(). Keine GATT-Schreibbefehle oder Authentifizierungsumgehung.
- Standardisierte GATT Device Information (0x180A): Hersteller 0x2A29, Modell 0x2A24, Seriennummer 0x2A25, Firmware 0x2A26, Hardware 0x2A27, Software 0x2A28, System-ID 0x2A23; Battery Level (0x180F/0x2A19) wenn angeboten. Rohbytes mit Quelle und UTC-Zeitstempel.
- Seriennummern-Abgleich: elektronischer Standard-GATT-Wert gegen manuelle Fahrzeugangabe. Wenn DIS nicht vorhanden, kein Vergleich; ein DIS-Wert kann eine andere Komponente bezeichnen.
- Regionshinweise ausschließlich aus manuell eingegebener G30-N4G-Seriennummer; Community-Zuordnung, kein Nachweis einer aktiven Region.
- Firmwarevergleich mit explizit manuell erfasster Quelle, kein Hersteller-Live-Katalog.
- CSV-Geschwindigkeitsanalyse aus **externen** Messwerten, nicht Fahrzeughistorie.
- JSON-Prüfbericht lokal und Druckansicht. Keine automatische Übertragung der Prüfdaten im App-Code. Hosting-Anbieter / Browser können Metadaten erhalten.

## Auf iPhone ausprobieren
1. Verzeichnis über eine eigene HTTPS-Seite bereitstellen (z. B. GitHub Pages) und URL in Bluefy öffnen.
2. Erst Demo, dann mit erlaubtem Fahrzeug bei Stillstand Bluetooth verbinden.
3. Falls keine GATT-DIS-Daten angezeigt werden, stellt das Gerät diese über die zugängliche Schnittstelle nicht bereit.
4. Ergebnisse nur als Erprobungsdaten nutzen. Keine Polizeifreigabe, keine forensische Validierung, keine sichere Manipulationserkennung.

## Datenschutz / Sicherheit
Seriennummern können personenbezogen sein. Bericht ausschließlich gemäß behördlichen Regeln behandeln. Hash im UI ist ein Integritätsprüfwert für den exportierten JSON-Inhalt, keine vertrauenswürdige Signatur oder Beweissicherungskette.

## Technische Referenzen
- Bluetooth SIG: GATT Device Information Service und Battery Service https://www.bluetooth.com/specifications/specs/
- Community-Dokumentation G30-Seriennummernschema: https://wiki.scooterhacking.org/doku.php?id=nbmax (nicht Herstellerreferenz)


## V1.3 – Lizenzcode-Freischaltung
Manuelle Dokumentation unabhängiger Hinweise mit Quellenpflicht. Keine automatische Erkennung, keine Eingabe echter Lizenzcodes, keine BLE-Schreiboperationen. Im JSON- und Druckbericht ist die Quellenlage als `licenseActivationAssessment` enthalten. Lizenzcode-Freischaltung kann mit der aktuellen lesenden GATT-Implementierung **nicht** nachgewiesen werden.
