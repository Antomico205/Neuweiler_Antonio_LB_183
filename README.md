# Neuweiler_Antonio_LB_183  

## Einleitung:
Der technologische Fortschritt der letzten Jahrzehnte hat sich als sehr hilfreich und entscheidend für den Datenaustausch erwiesen. In der heutigen Zeit sind die Daten einer Firma eines der wichtigsten, wenn nicht das wertvollste Gut. Dies umfasst allerdings nicht nur positive Aspekte, sondern birgt auch Risiken, da Betrüger und Hacker Schwachstellen in Systemen ausnutzen können.

Dies führte zu einem rasanten Wachstum im Bereich der Cybersecurity, da Firmen, sich vor Datenlecks und Diebstahl von geistigem Eigentum schützen möchten. 

In diesem Portfolioeintrag werde ich also das Katz und Maus Spiel zwischen einem Angreiffer und Applikationsentwickler näher bringen. Ich werde dadurch die im Modul 183 erreichten Handlungsziele vorstellen. 


Selbsteinschätzung:

Das Modul über Cybersecurity hat mir sehr gefallen, da ich schon immer mal wissen wollte wie das Thema aufgebaut ist und wie die Behebung von Sicherheitslücken funktioniert. Während dem Modul ist es mir ein wenig schwer gefallen mit dem Stoff mitzuhalten, da ich viele neue BEgriffe kennenlernen musste. Dadurch, dass ich mich mit dem gesammten Stoff der Leistungsbeurteilung befassen musste, half es mir Sachen zu verstehen, die ich beim ersten Mal nicht richtig verstanden habe. 
Da ich nicht alle Aufgaben der Leistungsbeurteilung erfüllt habe, würde ich aber dennoch behaupten das ich die wichtigen Zusammenhänge verstanden habe. 
## Handlungsziel 1: Momentane Sicherheitslücken

###Broken Access Control

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

# Security Misconfiguration

Sicherheitsfehlkonfigurationen sind die am häufigsten vorkommenden Sicherheitsprobleme. Sie können aus einer ganzen Reihe von Fehlern resultieren, darunter unzureichende Standardkonfigurationen, offene Cloud-Speicher, unnötig aktive Dienste, veraltete Softwareversionen oder Fehler in der Zugriffskontrolliste. Diese Schwachstellen können einem Angreifer Tür und Tor öffnen, um sich weiteren Zugriff auf das System zu verschaffen.

Gegenmaßnahmen:
1. Regelmäßige Sicherheitsaudits und -überprüfungen, um Fehlkonfigurationen zu identifizieren und zu beheben.
2. Automatisierung der Konfigurationsmanagementprozesse, um menschliche Fehler zu reduzieren.
3. Einsatz von Tools zur Verwaltung von Konfigurationen, die gewährleisten, dass nur genehmigte Änderungen vorgenommen werden.
4. Strenge Trennung von Test- und Produktionsumgebungen und Begrenzung der Zugriffe auf die Produktionsumgebung.

# Server-Side Request Forgery (SSRF)

Auch unter der Abkürzung SSRF bekannt, ermöglichen es einem Angreifer, den Server dazu zu bringen, Anfragen an interne Ressourcen zu senden, die der Angreifer normalerweise nicht erreichen kann. Das kann dazu führen, dass der Angreifer Zugriff auf interne Dienste innerhalb der Infrastruktur des Unternehmens erhält, Informationen ausspioniert oder manipulative Aktionen durchführt.

Gegenmaßnahmen: 
1. Beschränkung ausgehender Anfragen von Servern, um nur legitime und notwendige Ziele zu erlauben.
2. Einsatz von Firewalls und anderer Netzwerksicherheitsmechanismen, um nicht autorisierten Datenverkehr zu blockieren.
3. Verwendung sicherer Programmierpraktiken, um sicherzustellen, dass Eingaben validiert werden und externe Systemanfragen ordnungsgemäß gehandhabt werden.
4. Regelmäßiges Patching und Aktualisieren der Server-Software, um bekannte SSRF-Lücken zu schließen.


#Kritische Beurteilung: 

Die vier erwähnten Probleme sind nur die am häufigsten auftretende Probleme. Es gibt noch sehr viele weitere Bedrohungen.

# Handlungsziel 2: Sicherheitslücken und ihre Ursachen in einer Applikation erkennen und Gegenmassnahmen vorschlagen und implementieren können.

Um solch eine Sicherheitslücke aufzuzeigen, habe ich mich entschieden, mich auf das Login zu konzentrieren.

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/31b54e16-0dd7-4590-847a-f0d852978cc6)

Die Sicherheitslücke im Code liegt in der Verwendung der string.Format-Methode, um die SQL-Abfrage zu erstellen. Das direkte Einfügen von Benutzereingaben in SQL-Abfragen ohne ordnungsgemäße Validierung ermöglicht sogenannte SQL-Injection-Angriffe.
Wenn der Angreifer im Benutzerfeld diese Werte eingeben würde ![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/08ab2d9e-46d0-4d8c-aba2-4414bd4d8b30)
, hat dieser Zugang auf die Webseite. 

Beispiel an der Insecure App:

https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/fed700bb-424f-4224-a522-b3a164294908

Damit man dieses Problem beheben kann, kann man Parameterbindungen benutzen statt Benutzereingaben in die Abfrage einzufügen.

Dies habe ich mit mit diesem Codeabschnitt gelöst.
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/e99bc8f6-83f2-4d81-8e2d-ea4464ed96cc)

Beispiel nach der Problembehebung: 

https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/ea62893b-5319-4fa0-a9e2-95d3983b98ae

Aus diesem Grund ist es wichtig, den Code auf SQL Inhection zu prüfen.

#Beschreibung und Auswahl des Artefakt
Ich habe mich dazu entschieden ein Code Abschnitt der Insecure App auszuwählen, der zeigt wie die App auf diese SQL Injection geschützt ist.

#Nachweis 
Das Ziel wurde erreicht, da ich daie Sicherheitslücke erkannt habe und die oben gezeigte Gegenmassnahme eingesetzt habe. 

#Erklärung des Artefakts 
Im ersten Video sieht man, wie der Code mit der SQL Imjection sich mit den Benutzereingaben vermischt. Dies ist sehr gefählrich, da Angreiffer diese Eingaben manupulieren können.
Im zweiten Video ist es sicherer, da man die Datenbank versucht anzufragen. Der Code schützt also gefährliche Angriffe auf die erwähnte Sicherheitslücke.

#Kritische Beurteilung: 
Die SQL Injection wurde erklärt und eine Gegenmassnahme wurde eingesetzt. Eine andere Möglichkeit dieses Problem zu lösen, währe Cross Site Scripting.


# Handlungsziel 3: Mechanismen für die Autorisierung und Authentifizierung umsetzen können.

Eine Zwei-Faktor-Authentifizierung wurde nun in der Insecure App eingebunden. Dies führt dazu, das der Benutzer es aktivieren kann wenn er sich anmeldet. Ein QR-Code wird nach der nächsten Aktivierung erstellt, den der Nutzer mit dem Handy scannen kann. Hier benötigt man dazu die Authenticator App von Google. Dies muss man zuerst herunterladen, damit man die Aktivität fortsetzten kann.

Generierter QR-Code
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/47ba06b9-c8ef-436c-82b2-f6c0da17371b)

Hier befindet man sich auf der Login Seite, auf der man den erhaltenen 2FA-Code eingeben muss.
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/0878e7a7-69cb-4dd4-8883-0ee9f6a5da01)

Google Authenticator App auf dem Handy
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/92ce5add-ebc8-457e-9602-d37695eedc7a)

Implementierter Code 
Bei der ersten Anmeldung erfolgt eine Zwei-Faktor-Authentifizierung. Falls der Nutzer diesen Schritt getätigt hat, wird geprüft, ob der eingetragene Benutzerschlüssel übereinstimmt. 
Falls der Nutzer keine 2FA oder den Schlüssel falsch eingegeben hat, wird eine 401 Fehler meldung ausgegeben.
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/6157aa84-72a0-43c7-9819-fc2c81810176)
![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/3229fdcf-c583-4eaf-9e1b-2f4f0bc8ef0c)


# Autorisierung: 

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/ee5b48b5-689d-42bf-9428-c3622bfa5a11)

Die Autorisierung wird hier in der Applikation gezeigt. Hier wird überprüft, ob der angemeldete Nutzer die benötigten Berechtigungen hat, um konkrete Änderungen vorzunehmen. Somit wird hier getestet ob der Nutzer ein Admin oder ein gewöhnlicher User ist. Falls diese Anforderungen nicht erfüllt werden, werdem dem User manche Funktionen blockiert. (Zugriff blockiert)

#Auswahl und Beschreibung des Artefakts
Als Artefakt habe ich einen Codeabschnitt von der Insecure App genommen. Dieser zeigt, wie der Ablauf der Authentifizierung und Autorisierung funktioniert. Im verlauf von diesem Handlungsziel habe ich verschiedene Codeabschnitte eingefügt um zu verdäutliche wie dies funktioniert.

#Nachweis
Das implementieren der Zwei Faktor Authentifizierung in der Insecure App hat funktioniert. Somit habe ich das Ziel erreicht. Die Umsetzung der Autorisierung hat auch geklapt. Wenn sich der Nutzer anmelden möchte und die ID nicht richtig ist bedeutet das, das die Person nicht der Autor der erstellten Nachricht ist. 

#Erklärung des Artefakts 

#Authentifizierung
Der erste Codeabschnitt überprüft, ob der Nutzer die 2FA aktiviert hat und authentifiziert ihn anhand dem eingegebenen Schlüssel.
Im zweiten Codeabschnitt ist es für einen Nutzer möglich die 2FA zu aktivieren. Für den Nutzer wird dan ein neuen geheimen Schlüssel sowohl auch ein QR Code erstellt.

#Autorisierung
Im Codeabschnitt wird geschaut, ob der Nutzer ein Administrator ist oder nicht. Falls der Nutzer ein Administrator ist, hat er alle Admin Rechte die er nutzen kann. Falls die ID nicht mit dem Administrator der Nachricht übereinstimmt, hat dieser Nutzer keine Rechte diese Nachricht zu löschen.

#Kritische Beurteilung
In diesem Handlungsziel habe ich über die Zwei Faktor Authentifizierung und die Autorisierung erläutert und in meinem Projekt umgesetzt. 

# Handlungsziel 4: 

Viele Menschen tendieren zu einem zu einfachen Passwort, damit sie Zeit sparen. Viele User benutzen Passwörter wie: 12345 oder Passwort. Somit wird der Mensch selbst zur Sicherheitslücke, da man ein Passwort besitzt, dass einfach zu erraaten ist. 
Damit Benutzer vor zu einfachen Passwörter schützt, verfüght die Insecure App eine Funktion, die verscheidene Passwort Variationen verlangt

Code: 

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/32d22b62-66c2-4244-8653-f4091057f21e)

#Auswahl und Beschreibung des Artefakts

Als Artefakt habe ich einen Codeabschnitt aus der Insecure App ausgesucht, die aufzeigt wie sich die App vor dem menschlichen Faktor als Sicherheitslücke schützt.

#Nachweis der Zielreichung
Dadurch das ich die App sicher gegen den menschlichen Faktor gemacht habe wurde das Ziel erreicht.

#Erklärung des Artefakts
Im code ist ersichtlich, wie es sich voreinfachen Passwörter wie z.b Passwort oder 1234567890 schützt. So konnte die App dadurch geschützt werden.

#Kritische Beurteilung
Der menschliche Faktor wurde nur auf die Passwortwahl angepasst. Dadurch ist es nicht sicher da man immernoch durch Phishing in die App gelangen kann. (Bedeutet das der Nutzer auf eine falsche Webseite gelockt werden kann und dort das Passwort herausfinden kann.)


#Handlungsziel 5: 

Mit dem Hinzufügen von Loggin-Nachrichten ist es für Administratoren sowohl auch für Entwickler möglich wichtige Ereignisse in der Applikation zu sehen. Dies erleichtert die Nachverfolgung von Aktivitäten im System. Somit sind diese Protokolle für das Debuggen nützlich, da sie bei der Identifizierung von Problemen oder Sicherheitsvorfällen ersichtlich sind.

Code:

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/e159cd82-18ee-459f-8da6-07d6ae1bfb1c)


Konsolenansicht: 

![image](https://github.com/Antomico205/Neuweiler_Antonio_LB_183/assets/89131333/d9b91dbf-b19a-4db6-ae55-b3c511c661f6)

#Auswahl und Beschreibung des Artefakts
Als Artefakt habe ich ein Codeabschnitt ausgesucht, der aufzeigt, wie die Applikation auf Warnungen und Log Informationen umgeht und was er ausgibt.

#Nachweis 
Das Ziel wurde erreicht. Dies sieht man an der Ausgegebenen Konsolenausgabe.

#Erklärung des Artefakts 

Im falle, dass kein Benutzer gefunden wurde wird eine Log Warnung ausgegeben. Diese zeigt, das der Anmeldevorgang nicht funktioniert hat. 
Wenn sich ein Nutzer erfolgreich anmelden konnte, wird ein ok Status ausgegeben.





