# Neuweiler_Antonio_LB_183  

## Einleitung:
Der technologische Fortschritt der letzten Jahrzehnte hat sich als sehr hilfreich und entscheidend für den Datenaustausch erwiesen. In der heutigen Zeit sind die Daten einer Firma eines der wichtigsten, wenn nicht das wertvollste Gut. Dies umfasst allerdings nicht nur positive Aspekte, sondern birgt auch Risiken, da Betrüger und Hacker Schwachstellen in Systemen ausnutzen können.

Dies führte zu einem rasanten Wachstum im Bereich der Cybersecurity, da Firmen, sich vor Datenlecks und Diebstahl von geistigem Eigentum schützen möchten. 

In diesem Portfolioeintrag werde ich also das Katz und Maus Spiel zwischen Hacker und einem Applikationsentwickler näher bringen.

## Handlungsziel 1: Momentane Sicherheitslücken

### Broken Access Control

Wenn ein System nicht richtig überprüft, ob die Benutzer die richtigen Berechtigungen für den Zugriff auf bestimmte Daten oder Funktionen haben, tritt diese Bedrohung auf. Dadurch können Angreifer auf sensible Bereiche des Systems zugreifen. Somit können Daten geändert oder gelöscht werden ohne die benötigten Berechtigungen zu haben.

Gegenmaßnahmen: 
1. Implementierung einer rollenbasierten Zugriffskontrolle, um sicherzustellen, dass Benutzer nur auf die für ihre Rolle erforderlichen Ressourcen zugreifen können.
2. Prinzip der minimalen Rechte anwenden, d.h., Benutzer erhalten nur die minimal notwendigen Rechte, um ihre Aufgaben zu erfüllen.
3. Regelmäßige Überprüfung und Aktualisierung der Zugriffsrechte, um sicherzustellen, dass keine veralteten Berechtigungen bestehen bleiben.
4. Einsatz von Multi-Faktor-Authentifizierung, um die Sicherheit der Authentifizierung zu erhöhen.

### Cryptographic Failures

Dieses Problem bezieht sich auf die unzureichende Verschlüsselung oder den Schutz von sensiblen Daten. Dazu gehören Fehler wie die Verwendung veralteter oder unsicherer Kryptographieverfahren, das Offenlegen privater Schlüssel oder das Fehlen einer Verschlüsselung, wo sie notwendig wäre. Diese Versäumnisse können dazu führen, dass vertrauliche Informationen wie Passwörter, Finanzdaten oder persönliche Daten kompromittiert werden.

Gegenmaßnahmen: 
1. Verwendung aktueller und als sicher geltender Verschlüsselungsstandards für die Übertragung und Speicherung sensibler Daten.
2. Regelmäßige Überprüfung und Erneuerung von Zertifikaten und Schlüsselmaterialien.
3. Sichere Speicherung von Schlüsseln und Zertifikaten, um unautorisierten Zugriff zu verhindern.
4. Implementierung von Protokollen zur Früherkennung und Reaktion auf Datenlecks.

### Security Misconfiguration

Sicherheitsfehlkonfigurationen sind die am häufigsten vorkommenden Sicherheitsprobleme. Sie können aus einer ganzen Reihe von Fehlern resultieren, darunter unzureichende Standardkonfigurationen, offene Cloud-Speicher, unnötig aktive Dienste, veraltete Softwareversionen oder Fehler in der Zugriffskontrolliste. Diese Schwachstellen können einem Angreifer Tür und Tor öffnen, um sich weiteren Zugriff auf das System zu verschaffen.

Gegenmaßnahmen:
1. Regelmäßige Sicherheitsaudits und -überprüfungen, um Fehlkonfigurationen zu identifizieren und zu beheben.
2. Automatisierung der Konfigurationsmanagementprozesse, um menschliche Fehler zu reduzieren.
3. Einsatz von Tools zur Verwaltung von Konfigurationen, die gewährleisten, dass nur genehmigte Änderungen vorgenommen werden.
4. Strenge Trennung von Test- und Produktionsumgebungen und Begrenzung der Zugriffe auf die Produktionsumgebung.

### Server-Side Request Forgery (SSRF)

Auch unter der Abkürzung SSRF bekannt, ermöglichen es einem Angreifer, den Server dazu zu bringen, Anfragen an interne Ressourcen zu senden, die der Angreifer normalerweise nicht erreichen kann. Das kann dazu führen, dass der Angreifer Zugriff auf interne Dienste innerhalb der Infrastruktur des Unternehmens erhält, Informationen ausspioniert oder manipulative Aktionen durchführt.

Gegenmaßnahmen: 
1. Beschränkung ausgehender Anfragen von Servern, um nur legitime und notwendige Ziele zu erlauben.
2. Einsatz von Firewalls und anderer Netzwerksicherheitsmechanismen, um nicht autorisierten Datenverkehr zu blockieren.
3. Verwendung sicherer Programmierpraktiken, um sicherzustellen, dass Eingaben validiert werden und externe Systemanfragen ordnungsgemäß gehandhabt werden.
4. Regelmäßiges Patching und Aktualisieren der Server-Software, um bekannte SSRF-Lücken zu schließen.

## Handlungsziel 2:

Um solch eine Sicherheitslücke aufzuzeigen, habe ich mich entschieden, mich auf das Login zu konzentrieren.

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/31b54e16-0dd7-4590-847a-f0d852978cc6)

Die Sicherheitslücke im Code liegt in der Verwendung der string.Format-Methode, um die SQL-Abfrage zu erstellen. Das direkte Einfügen von Benutzereingaben in SQL-Abfragen ohne ordnungsgemäße Validierung ermöglicht sogenannte SQL-Injection-Angriffe.

https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/fed700bb-424f-4224-a522-b3a164294908


## Handlungsziel 3:

Erklären Sie das Artefakt in wenigen Sätzen. Sollte das Artefakt mehrere Handlungsziele beinhalten dürfen Sie die Erklärung auch zusammenfassen.

## Handlungsziel 4: 

Beurteilen Sie die Umsetzung Ihres Artefakts im Hinblick auf das Handlungsziel kritisch. Sollten gewisse Aspekte des Handlungsziels fehlen, haben Sie die Möglichkeit, in diesem Teil darauf einzugehen.

## Reflexion:




