# Neuweiler_Antonio_LB_183  

## Einleitung:
-----------------------------
Der technologische Fortschritt der letzten Jahrzehnte hat sich als sehr hilfreich und entscheidend für den Datenaustausch erwiesen. In der heutigen Zeit sind die Daten einer Firma eines der wichtigsten, wenn nicht das wertvollste Gut. Dies umfasst allerdings nicht nur positive Aspekte, sondern birgt auch Risiken, da Betrüger und Hacker Schwachstellen in Systemen ausnutzen können.

Dies führte zu einem rasanten Wachstum im Bereich der Cybersecurity, da Firmen, sich vor Datenlecks und Diebstahl von geistigem Eigentum schützen möchten. 

In diesem Prortfolioeintrag werde ich also das Katz und Maus Spiel zwischen Hacker und einem Applikations Entwicker näher bringen.

## Handlungsziel 1: Momentane Sicherheitslücken
-----------------------------

Broken Access Control

Wenn ein System nicht richtig überprüft, ob die Benutzer die richtigen Berechtigungen für den Zugriff auf bestimmte Daten oder Funktionen haben, tritt diese Bedrohung auf. Dadurch können Angreiffer auf sensible Bereiche des Systems zugreiffen. Somit können  Daten geändert oder gelöscht werden ohne die benötigten Berechtigungen zu haben.

https://www.google.ch/url?sa=i&url=https%3A%2F%2Fpractonet.com%2Fbroken-access-control%2F&psig=AOvVaw1mzTlfaq_iK8HZ8uHXcgvm&ust=1702928925619000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCNiOlOOel4MDFQAAAAAdAAAAABAI

Gegenamssnahmen: 
1. Implementierung einer rollenbasierten Zugriffskontrolle, um sicherzustellen, dass Benutzer nur auf die für ihre Rolle erforderlichen Ressourcen zugreifen können.
2. Prinzip der minimalen Rechte anwenden, d.h., Benutzer erhalten nur die minimal notwendigen Rechte, um ihre Aufgaben zu erfüllen.
3. Regelmäßige Überprüfung und Aktualisierung der Zugriffsrechte, um sicherzustellen, dass keine veralteten Berechtigungen bestehen bleiben.
4. Einsatz von Multi-Faktor-Authentifizierung, um die Sicherheit der Authentifizierung zu erhöhen.


Cryptographic Failures:

Dieses Problem bezieht sich auf die unzureichende Verschlüsselung oder den Schutz von sensiblen Daten. Dazu gehören Fehler wie die Verwendung veralteter oder unsicherer Kryptographieverfahren, das Offenlegen privater Schlüssel oder das Fehlen einer Verschlüsselung, wo sie notwendig wäre. Diese Versäumnisse können dazu führen, dass vertrauliche Informationen wie Passwörter, Finanzdaten oder persönliche Daten kompromittiert werden.

https://www.google.ch/url?sa=i&url=https%3A%2F%2Fwww.freecodecamp.org%2Fnews%2Fwhy-does-cryptographic-software-fail-often-d660d3cdfdc5%2F&psig=AOvVaw1dHn_wLwS7F0YstLQjZ6Kj&ust=1702929137681000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCMCh-cufl4MDFQAAAAAdAAAAABAH

Gegenamssnahmen: 
1. Verwendung aktueller und als sicher geltender Verschlüsselungsstandards für die Übertragung und Speicherung sensibler Daten.
2. Regelmäßige Überprüfung und Erneuerung von Zertifikaten und Schlüsselmaterialien.
3. Sichere Speicherung von Schlüsseln und Zertifikaten, um unautorisierten Zugriff zu verhindern.
4. Implementierung von Protokollen zur Früherkennung und Reaktion auf Datenlecks.
   
Security Misconfiguration 

Sicherheitsfehlkonfigurationen sind die am häufigsten vorkommenden Sicherheitsprobleme. Sie können aus einer ganzen Reihe von Fehlern resultieren, darunter unzureichende Standardkonfigurationen, offene Cloud-Speicher, unnötig aktive Dienste, veraltete Softwareversionen oder Fehler in der Zugriffskontrolliste. Diese Schwachstellen können einem Angreifer Tür und Tor öffnen, um sich weiteren Zugriff auf das System zu verschaffen.

https://www.google.ch/url?sa=i&url=https%3A%2F%2Fwww.aquasec.com%2Fcloud-native-academy%2Fsupply-chain-security%2Fsecurity-misconfigurations%2F&psig=AOvVaw0x8OKXbmFXKmO_9WstHM1Y&ust=1702992121214000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOie6paKmYMDFQAAAAAdAAAAABAD

Gegenmassnahmen:
1. Regelmäßige Sicherheitsaudits und -überprüfungen, um Fehlkonfigurationen zu identifizieren und zu beheben.
2. Automatisierung der Konfigurationsmanagementprozesse, um menschliche Fehler zu reduzieren.
3. Einsatz von Tools zur Verwaltung von Konfigurationen, die gewährleisten, dass nur genehmigte Änderungen vorgenommen werden.
4. Strenge Trennung von Test- und Produktionsumgebungen und Begrenzung der Zugriffe auf die Produktionsumgebung.
   
Server-Side Request Forgery 

Auch unter der Abkürzung SSRF bekannt ermöglichen es einem Angreifer, den Server dazu zu bringen, Anfragen an interne Ressourcen zu senden, die der Angreifer normalerweise nicht erreichen kann. Das kann dazu führen, dass der Angreifer Zugriff auf interne Dienste innerhalb der Infrastruktur des Unternehmens erhält, Informationen ausspioniert oder manipulative Aktionen durchführt.

https://www.google.ch/url?sa=i&url=https%3A%2F%2Fwww.geeksforgeeks.org%2Fserver-side-request-forgery-ssrf-in-depth%2F&psig=AOvVaw0_w8WecvU66hiXtYQ97ifz&ust=1702992297902000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCMDM7umKmYMDFQAAAAAdAAAAABAD

Gegenmassnahmen: 
1. Beschränkung ausgehender Anfragen von Servern, um nur legitime und notwendige Ziele zu erlauben.
2. Einsatz von Firewalls und anderer Netzwerksicherheitsmechanismen, um nicht autorisierten Datenverkehr zu blockieren.
3. Verwendung sicherer Programmierpraktiken, um sicherzustellen, dass Eingaben validiert werden und externe Systemanfragen ordnungsgemäß gehandhabt werden.
4. Regelmäßiges Patching und Aktualisieren der Server-Software, um bekannte SSRF-Lücken zu schließen.

   
Handlungsziel 2:
-----------------------------
Weisen Sie nach, wie Sie das Handlungsziel erreicht haben. Verweisen Sie dabei auf das von Ihnen erstellte Artefakt. Das Artefakt muss im ePortfolio sichtbar oder verlinkt sein.

Handlungsziel 3:
-----------------------------
Erklären Sie das Artefakt in wenigen Sätzen. Sollte das Artefakt mehrere Handlungsziele beinhalten dürfen Sie die Erklärung auch zusammenfassen.

Handlungsziel 4: 
-----------------------------
Beurteilen Sie die Umsetzung Ihres Artefakts im Hinblick auf das Handlungsziel kritisch. Sollten gewisse Aspekte des Handlungsziels fehlen, haben Sie die Möglichkeit, in diesem Teil darauf einzugehen.

Reflexion:
-----------------------------
