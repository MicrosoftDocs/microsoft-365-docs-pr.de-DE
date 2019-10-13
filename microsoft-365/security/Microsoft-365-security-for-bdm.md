---
title: Microsoft 365 Security for Business-Entscheidungsträger (BDMs)
ms.author: bcarter
author: brendacarter
manager: ''
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: die häufigsten Bedrohungs-und Angriffsszenarien, mit denen Organisationen derzeit in Ihren Microsoft 365-Umgebungen konfrontiert sind, sowie Empfohlene Aktionen zur Minderung dieser Risiken.
ms.openlocfilehash: 16108f71702e2464721fa09fee4c6c298496a2c4
ms.sourcegitcommit: 6ef9a98e3d9de44ee4f01870f9189fa676572419
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2019
ms.locfileid: "37481350"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business-Entscheidungsträger (BDMs)

In diesem Artikel werden einige der häufigsten Bedrohungs-und Angriffsszenarien behandelt, denen Organisationen für Ihre Microsoft 365-Umgebungen derzeit ausgesetzt sind, sowie Empfohlene Aktionen zur Minderung dieser Risiken. Während Microsoft 365 mit einer breiten Palette vorkonfigurierter Sicherheitsfeatures ausgeliefert wird, müssen Sie als Kunde auch die Verantwortung übernehmen, um Ihre eigenen Identitäten, Daten und Geräte zu schützen, die für den Zugriff auf Cloud-Dienste verwendet werden. 

Dieser Artikel ist nach Priorität von Arbeit organisiert, beginnend mit dem Schutz dieser Konten, die für die Verwaltung der kritischsten Dienste und Ressourcen verwendet werden, beispielsweise Ihres Mandanten, ihrer e-Mail und SharePoint. Sie bietet eine methodische Möglichkeit zur Annäherung an Sicherheit und arbeitet mit der folgenden Tabelle zusammen, damit Sie Ihren Fortschritt mit Beteiligten und Teams in Ihrer Organisation verfolgen können: [Microsoft 365 Security for BDMs Spreadsheet](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![Thumb Image Microsoft 365 BDM Security Recommendations Spreadsheet](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft stellt Ihnen das sichere Bewertungstool in Ihrem Mandanten zur Verfügung, mit dem Sie Ihre Sicherheitsposition basierend auf Ihren regulären Aktivitäten automatisch analysieren, eine Bewertung zuweisen und Empfehlungen zur Sicherheitsverbesserung stellen können. Beachten Sie vor dem Ausführen der in diesem Artikel empfohlenen Aktionen die aktuellen Ergebnisse und Empfehlungen. Die in diesem Artikel empfohlenen Aktionen verbessern Ihre Punktzahl. Ziel ist nicht die maximale Punktzahl, sondern die Möglichkeiten zum Schutz Ihrer Umgebung, die sich nicht negativ auf die Produktivität Ihrer Benutzer auswirken. Siehe [Microsoft Secure Score](mtp/microsoft-secure-score.md).

Noch eine Sache, bevor wir anfangen. . . Achten Sie darauf, [das Office 365 Überwachungsprotokoll einzuschalten](../compliance/search-the-audit-log-in-security-and-compliance.md). Sie benötigen diese Daten später, für den Fall, dass Sie einen Vorfall oder eine Verletzung untersuchen müssen. 

## <a name="protect-privileged-accounts"></a>Schützen von privilegierten Konten

Als ersten Schritt wird empfohlen, sicherzustellen, dass wichtige Konten in der Umgebung eine zusätzliche Schutzebene erhalten, da diese Konten Zugriff und Berechtigungen zum Verwalten und ändern wichtiger Dienste und Ressourcen haben, die sich negativ auf die gesamte Organisation auswirken können. Wenn kompromittiert. Das Schützen von privilegierten Konten ist eine der effektivsten Methoden zum Schutz gegen einen Angreifer, der versucht, die Berechtigungen eines kompromittierten Kontos auf einen Administrator zu erhöhen. 

|Empfehlung  |E3 |E5  |
|---------|---------|---------|
|Erzwingen Sie die mehrstufige Authentifizierung (MFA) für alle Administratorkonten.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)| 
|Implementieren Sie Azure Active Directory (Azure AD) Privileged Identity Management (PIM), um just-in-Time-privilegierten Zugriff auf Azure AD-und Azure-Ressourcen anzuwenden. Sie können auch ermitteln, wer Zugriff hat, und überprüfen Sie den privilegierten Zugriff.|         | ![grünes Häkchen](../images/green-check-mark.png)|
|Implementieren einer privilegierten Zugriffsverwaltung in Office 365 zum Verwalten der granularen Zugriffssteuerung über privilegierte Administratoraufgaben in Office 365. |         | ![grünes Häkchen](../images/green-check-mark.png)|
|Konfigurieren und Verwenden von PAW (privileged Access Workstations) zum Verwalten von Diensten. Verwenden Sie nicht die gleichen Arbeitsstationen zum Durchsuchen des Internets und zum Überprüfen von e-Mails, die nicht mit Ihrem Administratorkonto in Zusammenhangstehen.|  ![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png) | 

Das folgende Diagramm veranschaulicht diese Funktionen.
![Empfohlene Funktionen zum Schutz von privilegierten Konten](../images/m365-security-bdm-illustrations-privileged-accounts.png)

Weitere Empfehlungen:
- Stellen Sie sicher, dass Konten, die von lokal synchronisiert werden, nicht den Administratorrollen für Cloud-Dienste zugewiesen sind. Dadurch kann verhindert werden, dass ein Angreifer lokale Konten nutzt, um administrativen Zugriff auf Cloud-Dienste zu erhalten. 
- Stellen Sie sicher, dass Dienstkonten keine Administratorrollen zugewiesen sind. Diese Konten werden häufig nicht überwacht und mit Kennwörtern festgelegt, die nicht ablaufen. Stellen Sie zunächst sicher, dass die AADConnect-und ADFS-Dienste-Konten standardmäßig keine globalen Administratoren sind.
- Entfernen von Lizenzen von Administratorkonten. Wenn es keinen bestimmten Benutzer Fall gibt, um Lizenzen bestimmten Administratorkonten zuzuweisen, entfernen Sie Lizenzen von diesen Konten. 

## <a name="reduce-the-surface-of-attack"></a>Verringern der Angriffsfläche

Im nächsten Fokusbereich wird die Angriffsfläche reduziert. Dies kann mit minimalem Aufwand und Auswirkungen auf Ihre Benutzer und Dienste erreicht werden. Durch die Verringerung der Angriffsfläche haben Angreifer weniger Möglichkeiten, einen Angriff auf Ihre Organisation zu starten.

Im Folgenden finden Sie einige Beispiele:
- Deaktivieren Sie POP3-, IMAP-und SMTP-Protokolle. Die meisten modernen Organisationen verwenden diese älteren Protokolle nicht mehr. Sie können diese sicher deaktivieren und bei Bedarf nur Ausnahmen zulassen. 
- Verringern Sie die Anzahl globaler Administratoren im Mandanten, und halten Sie Sie auf das absolut erforderliche Minimum. Dadurch wird die Angriffsfläche für alle Cloud-Anwendungen direkt reduziert. 
- Zurückziehen von Servern und Anwendungen, die in Ihrer Umgebung nicht mehr verwendet werden. 
- Implementieren Sie einen Prozess zum Deaktivieren und Löschen von Konten, die nicht mehr verwendet werden. 

## <a name="protect-against-known-threats"></a>Schutz vor bekannten Bedrohungen

Zu den bekannten Bedrohungen gehören Schadsoftware, kompromittierte Konten und Phishing. Einige Schutzmaßnahmen gegen diese Bedrohungen können schnell ohne direkte Auswirkungen auf die Benutzer implementiert werden, während andere mehr Planung und Benutzerschulung erfordern. 

|Empfehlung  |E3  |E5  |
|---------|---------|---------|
|**Einrichten der mehrstufigen Authentifizierung und Verwenden von empfohlenen Richtlinien für den bedingten Zugriff, einschließlich der Anmelde Risikorichtlinien**. Microsoft empfiehlt und hat eine Reihe von Richtlinien getestet, die zusammenarbeiten, um alle Cloud-apps zu schützen, einschließlich Office 365 und Microsoft 365-Dienste. Siehe [Konfigurationen für den Identitäts-und Geräte Zugriff](../enterprise/microsoft-365-policies-configurations.md). | |![grünes Häkchen](../images/green-check-mark.png)|
|**Mehrstufige Authentifizierung für alle Benutzer erforderlich**. Wenn Sie nicht über die erforderliche Lizenzierung zum Implementieren der empfohlenen Richtlinien für den bedingten Zugriff verfügen, benötigen Sie mindestens die mehrstufige Authentifizierung für alle Benutzer.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|**Erhöhen Sie das Schutzniveau vor Schadsoftware in Mail**. Ihre Office 365-oder Microsoft 365-Umgebung umfasst Schutz vor Schadsoftware, aber Sie können diesen Schutz verbessern, indem Sie Anlagen mit Dateitypen blockieren, die häufig für Schadsoftware verwendet werden.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|**Schützen Sie Ihre e-Mails vor gezielten Phishing-Angriffen**. Wenn Sie eine oder mehrere benutzerdefinierte Domänen für Ihre Office 365-oder Microsoft 365-Umgebung konfiguriert haben, können Sie den gezielten Schutz gegen Phishing konfigurieren. Der ATP-Schutz gegen Phishing, ein Teil Office 365 Advanced Threat Protection, kann zum Schutz Ihrer Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Phishing-Angriffen beitragen. Wenn Sie keine benutzerdefinierte Domäne konfiguriert haben, müssen Sie dies nicht tun.| |![grünes Häkchen](../images/green-check-mark.png)|
|**Schützen Sie sich vor Ransomware-Angriffen in e-Mails**. Ransomware nimmt den Zugriff auf Ihre Daten durch Verschlüsseln von Dateien oder Sperren von Computerbildschirmen in Anspruch. Er versucht dann, Geld von den Opfern zu erpressen, indem er nach "Lösegeld" fragt, normalerweise in Form von cryptocurrencies wie Bitcoin, im Gegenzug zum Zurückgeben des Zugriffs auf Ihre Daten. Sie können zur Verteidigung gegen Ransomware beitragen, indem Sie eine oder mehrere Nachrichtenfluss Regeln erstellen, um Dateierweiterungen zu blockieren, die in der Regel für Ransomware verwendet werden, oder um Benutzer zu warnen, die diese Anlagen in e-Mails empfangen.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|**Blockieren Sie Verbindungen aus Ländern, mit denen Sie nicht Geschäfte machen**. Erstellen Sie eine Azure AD Richtlinie für den bedingten Zugriff, um alle Verbindungen zu blockieren, die aus diesen Ländern stammen, und erstellen Sie effektiv eine Geo-Firewall um ihren Mandanten.| |![grünes Häkchen](../images/green-check-mark.png)|

Das folgende Diagramm veranschaulicht diese Funktionen.
![Empfohlene Funktionen zum Schutz vor bekannten Bedrohungen](../images/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Schutz vor unbekannten Bedrohungen

Nachdem Sie Ihren privilegierten Konten zusätzlichen Schutz und Schutz vor bekannten Angriffen hinzugefügt haben, sollten Sie Ihre Aufmerksamkeit auf den Schutz vor unbekannten Bedrohungen lenken. Die entschlosseneren und anspruchsvolleren Gegner verwenden innovative und neue, unbekannte Methoden, um Organisationen anzugreifen. Mit der umfangreichen Telemetrie von Microsoft, die über Milliarden von Geräten, Anwendungen und Diensten gesammelt wurde, können wir fortschrittlichen Bedrohungsschutz für Windows, Office 365 und Azure durchführen, um gegen Zero-Day-Angriffe zu verhindern, indem Sie sandkastenumgebungen nutzen und Überprüfen der Gültigkeit, bevor Sie Zugriff auf Ihre Inhalte gewähren. 


|Empfehlung  |E3  |E5  |
|---------|---------|---------|
|**Konfigurieren Office 365 Advanced Threat Protection (ATP)**:<br>• Sichere ATP-Anhänge<br>• ATP-sichere Links<br>• ATP für SharePoint, OneDrive und Microsoft Teams<br>• ATP-Schutz gegen Phishing|         |![grünes Häkchen](../images/green-check-mark.png) |
|**Konfigurieren von Microsoft Defender Advanced Threat Protection-Funktionen**:<br>• Windows Defender-Antivirus <br>• Schutz vor Ausnutzung <br> • Reduzierung der Angriffsfläche <br> • Hardware basierte Isolierung <br>• Kontrollierter Ordner Zugriff     |         |![grünes Häkchen](../images/green-check-mark.png) |
|**Verwenden Sie die Microsoft Cloud-App-Sicherheit** , um SaaS-apps zu entdecken und mit der Verhaltensanalyse und Anomalien-Erkennung zu beginnen. |         |![grünes Häkchen](../images/green-check-mark.png) |

Das folgende Diagramm veranschaulicht diese Funktionen.
![Empfohlene Funktionen zum Schutz vor unbekannten Bedrohungen](../images/m365-security-bdm-illustrations-unknown-threats.png)

Weitere Empfehlungen:
- Sichere partnerkanal Kommunikation wie e-Mails mit TLS.
- Öffnen Sie den Teams-Partnerverbund nur für Partner, mit denen Sie kommunizieren.
- Listen Sie keine Absenderdomänen, einzelne Absender oder Quell-IPs auf, da dadurch Spam-und Malware Überprüfungen umgangen werden können – eine gängige Vorgehensweise bei Kunden ist die Whitelist ihrer eigenen akzeptierten Domänen oder einer Reihe von anderen Domänen, in denen e-Mail-Fluss Probleme aufgetreten sind. gemeldet. Fügen Sie keine Domänen in die Liste der Spam-und Verbindungsfilterung ein, da dadurch möglicherweise alle Spam Überprüfungen umgangen werden. 
- Ausgehende Spambenachrichtigungen aktivieren: Aktivieren Sie ausgehende Spambenachrichtigungen in einer Verteilerliste intern an das Helpdesk-oder IT-Verwaltungsteam, um zu melden, ob externe Spam-e-Mails von einem der internen Benutzer extern gesendet werden. Dies kann ein Indikator dafür sein, dass das Konto kompromittiert wurde.
- Deaktivieren von Remote-PowerShell für alle Benutzer – Remote-PowerShell wird hauptsächlich von Administratoren für den Zugriff auf Office 365 Dienste zu administrativen Zwecken oder für den programmatischen API-Zugriff verwendet. Wir empfehlen, diese Option für nicht-Administrator-Benutzer zu deaktivieren, um eine Aufklärung zu vermeiden, es sei denn, Sie haben eine geschäftliche Anforderung für den Zugriff darauf. 
- Blockieren des Zugriffs auf das Microsoft Azure Verwaltungsportal für alle nicht-Administratoren. Sie können dies erreichen, indem Sie eine Regel für bedingten Zugriff erstellen, um alle Benutzer zu blockieren, mit Ausnahme von Administratoren. 


## <a name="assume-breach"></a>Annahme einer Verletzung

Während Microsoft alle möglichen Maßnahmen zur Abwehr von Bedrohungen und Angriffen durchführt, wird empfohlen, immer unter der Denkweise "Übernehmen einer Verletzung" zu arbeiten. Selbst wenn ein Angreifer in die Umgebung eindringen konnte, müssen wir sicherstellen, dass er keine Daten oder Identitätsinformationen aus der Umgebung exfiltrieren kann. Aus diesem Grund wird empfohlen, Schutz vor vertraulichen Datenverlusten wie Sozialversicherungsnummern, Kreditkartennummern, zusätzlichen persönlichen Informationen und anderen vertraulichen Informationen auf Organisationsebene zu aktivieren. 

Die Denkweise "Annehmen einer Verletzung" erfordert die Implementierung einer NULL-vertrauenswürdigen Netzwerk Strategie, was bedeutet, dass Benutzer nicht vollständig vertrauenswürdig sind, nur weil Sie intern im Netzwerk sind. Stattdessen werden im Rahmen der Autorisierung, was Benutzer tun können, festgelegte Bedingungen angegeben, und wenn solche Bedingungen erfüllt sind, werden bestimmte Steuerelemente erzwungen. Die Bedingungen können den Geräte Integritätsstatus, den Zugriff auf die Anwendung, den ausgeführten Betrieb und das Benutzer Risiko umfassen. Beispielsweise sollte eine Geräte Registrierungsaktion immer die MFA-Authentifizierung auslösen, um sicherzustellen, dass der Umgebung keine Rouge-Geräte hinzugefügt werden. 

Für eine NULL-vertrauenswürdige Netzwerk Strategie müssen Sie auch wissen, wo Ihre Informationen gespeichert sind, und geeignete Steuerelemente für Klassifizierung, Schutz und Aufbewahrung anwenden. Um Ihre kritischsten und vertraulichen Ressourcen effektiv zu schützen, müssen Sie zuerst herausfinden, wo sich diese befinden und wie Sie inventarisieren, was eine Herausforderung darstellen kann. Als nächstes arbeiten Sie mit Ihrer Organisation zusammen, um eine Steuerungsstrategie zu definieren. Das Definieren eines Klassifikationsschemas für eine Organisation und das Konfigurieren von Richtlinien, Bezeichnungen und Bedingungen erfordert eine sorgfältige Planung und Vorbereitung. Es ist wichtig zu wissen, dass es sich dabei nicht um einen IT-basierten Prozess handelt. Stellen Sie sicher, dass Sie mit Ihrem Legal and Compliance-Team zusammenarbeiten, um ein geeignetes Klassifizierungs-und Kennzeichnungs Schema für die Daten Ihrer Organisation zu entwickeln.

Microsoft 365 Information Protection-Funktionen können Ihnen dabei helfen herauszufinden, welche Informationen Sie haben, wo Sie gespeichert sind und welche Informationen zusätzlichen Schutz erfordern. Der Informationsschutz ist ein kontinuierlicher Prozess, und Microsoft 365-Funktionen bieten Ihnen Einblick in die Verwendung und Verteilung von vertraulichen Informationen durch Benutzer, wo Ihre Informationen aktuell gespeichert werden und wo Sie fließt. Sie können auch sehen, wie Benutzer mit Informationen umgehen, die reguliert werden, um sicherzustellen, dass die entsprechenden Bezeichnungen und Schutzmechanismen angewendet werden.


|Empfehlung |E3|E5 |
|---------|---------|---------|
|**Überprüfen und optimieren Sie Ihren bedingten Zugriff und zugehörige Richtlinien, damit Sie sich an Ihre Ziele für ein Zero-Trust-Netzwerk ausrichten können**. Zum Schutz vor bekannten Bedrohungen gehört das Implementieren einer Reihe [empfohlener Richtlinien](../enterprise/microsoft-365-policies-configurations.md). Überprüfen Sie Ihre Implementierung dieser Richtlinien, um sicherzustellen, dass Sie Ihre apps und Daten vor Hackern schützen, die Zugriff auf Ihr Netzwerk erlangt haben. Beachten Sie, dass die empfohlene InTune-App-Schutzrichtlinie für Windows 10 Windows Information Protection (WIP) aktiviert. WIP schützt vor versehentlichen Verlusten ihrer Organisationsdaten über apps und Dienste wie e-Mail, soziale Netzwerke und die öffentliche Cloud. |         |![grünes Häkchen](../images/green-check-mark.png)|
|**Externe e-Mail-Weiterleitung deaktivieren**. Hacker, die Zugriff auf das Postfach eines Benutzers erhalten, können Ihre e-Mails stehlen, indem Sie das Postfach so festlegen, dass e-Mails automatisch weitergeleitet werden. Dies kann auch ohne das Bewusstsein des Benutzers geschehen. Sie können dies verhindern, indem Sie eine e-Mail-Fluss Regel konfigurieren.|![grünes Häkchen](../images/green-check-mark.png) |![grünes Häkchen](../images/green-check-mark.png)|
|**Anonyme externe Kalenderfreigabe deaktivieren**. Standardmäßig ist die externe anonyme Kalenderfreigabe zulässig. [Deaktivieren Sie die Kalenderfreigabe](https://docs.microsoft.com/en-us/exchange/sharing/sharing-policies/modify-a-sharing-policy) , um potenzielle Lecks an vertraulichen Informationen zu verringern.|![grünes Häkchen](../images/green-check-mark.png) |![grünes Häkchen](../images/green-check-mark.png)|
|**Konfigurieren von Richtlinien zur Verhinderung von Datenverlust für vertrauliche Daten** Erstellen Sie eine Richtlinie zur Verhinderung von Datenverlust im Office 365 Security and Compliance Center, um vertrauliche Daten wie Kreditkartennummern, Sozialversicherungsnummern und Kontonummern zu ermitteln und zu schützen. Office 365 enthält zahlreiche vordefinierte Typen vertraulicher Informationen, die Sie in Richtlinien zur Verhinderung von Datenverlust verwenden können. Sie können auch eigene vertrauliche Informationstypen für vertrauliche Daten erstellen, die für Ihre Umgebung Benutzerdefiniert sind. |![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|**Implementieren von Daten Klassifizierungs-und Informationsschutz Richtlinien** Implementieren Sie Sensitivitäts Bezeichnungen in Office 365, und verwenden Sie diese, um Schutz auf vertrauliche Daten zu klassifizieren und anzuwenden. Sie können diese Bezeichnungen auch in Richtlinien zur Verhinderung von Datenverlust verwenden. Wenn Sie Azure Information Protection-Bezeichnungen verwenden, sollten Sie vermeiden, neue Bezeichnungen in anderen Verwaltungszentren zu erstellen.|         |![grünes Häkchen](../images/green-check-mark.png)|
|**Schützen von Daten in Drittanbieter-apps und-Diensten mithilfe der Cloud-App-Sicherheit**. Konfigurieren von Cloud-App-Sicherheitsrichtlinien zum Schutz vertraulicher Informationen in Cloud-apps von Drittanbietern wie Salesforce, Box oder Dropbox. Sie können vertrauliche Informationstypen und die in Office 365 erstellten Vertraulichkeits Bezeichnungen in Cloud-App-Sicherheitsrichtlinien verwenden und diese auf Ihre SaaS-apps anwenden. <br><br>Mit der Microsoft Cloud-App-Sicherheit können Sie eine Vielzahl von automatisierten Prozessen erzwingen. Richtlinien können festgelegt werden, um kontinuierliche Konformitätsscans, gesetzliche eDiscovery-Aufgaben, DLP für öffentlich freigegebene vertrauliche Inhalte und vieles mehr bereitzustellen. Die Cloud-App-Sicherheit kann jeden Dateityp überwachen, der auf mehr als 20 Metadaten-Filtern basiert (beispielsweise Zugriffsebene, Dateityp). |         |![grünes Häkchen](../images/green-check-mark.png)|
|**Verwenden Sie [Microsoft Defender ATP](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) , um festzustellen, ob Benutzer vertrauliche Informationen auf Ihren Windows-Geräten speichern**. |         |![grünes Häkchen](../images/green-check-mark.png)|
|**Verwenden Sie den [AIP-Scanner](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) zum Identifizieren und Klassifizieren von Informationen über Server und Dateifreigaben hinweg**. Verwenden Sie das AIP-Berichtstool, um die Ergebnisse anzuzeigen und entsprechende Aktionen durchführen zu können.|         |![grünes Häkchen](../images/green-check-mark.png)|

Das folgende Diagramm veranschaulicht diese Funktionen.
![Empfohlene Funktionen zum Schutz vor Verstößen](../images/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Kontinuierliche Überwachung und Überwachung

Die letzte, aber nicht zuletzt kontinuierliche Überwachung und Überwachung der Microsoft 365-Umgebung zusammen mit den Fenstern und Geräten ist wichtig, um sicherzustellen, dass Sie Eindringlinge schnell erkennen und beheben können. Tools wie Secure Score, Security Center und Advanced Analytics von Microsoft Intelligent Graph bieten unschätzbare Informationen in Ihrem Mandanten und verknüpfen riesige Mengen an Threat Intelligence-und Sicherheitsdaten, um Ihnen einen unübertroffenen Bedrohungsschutz zu bieten. und-Erkennung.


|Empfehlung |E3 |E5 |
|---------|---------|---------|
|Stellen Sie sicher, dass das **Office 365 Überwachungsprotokoll** aktiviert ist.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|**Review Secure Score Weekly** — Secure Score ist ein zentraler Ort, um auf den Sicherheitsstatus Ihres Office 365 Mandanten zuzugreifen und Aktionen basierend auf Tipps für sichere Bewertungen durchführen zu können. Es wird empfohlen, diese Überprüfung wöchentlich durchzuführen.|![grünes Häkchen](../images/green-check-mark.png)|![grünes Häkchen](../images/green-check-mark.png)|
|Verwenden Sie **Office 365 ATP** -Tools:<br>• Untersuchung und Antwortfunktionen für Bedrohungen<br> • Automatische Untersuchung und Antwort |         |![grünes Häkchen](../images/green-check-mark.png)|
|Verwenden Sie **Microsoft Defender ATP**:<br> • [Endpunkterkennung und-Antwort](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> • Sichere Bewertung für automatisierte Untersuchungen und Korrekturen <br>• [Erweiterte Suche](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![grünes Häkchen](../images/green-check-mark.png)|
|Verwenden Sie **Microsoft Cloud App Security** , um ungewöhnliches Verhalten in Cloud-apps zu erkennen, um Ransomware, kompromittierte Benutzer oder nicht autorisierte Anwendungen zu identifizieren, die Verwendung von hohem Risiko zu analysieren und automatisch zu beheben, um das Risiko für Ihre Organisation zu begrenzen.|         |![grünes Häkchen](../images/green-check-mark.png)|
|Verwenden Sie **Microsoft Azure Sentinel** oder Ihr **Aktuelles Siem** -Tool, um Bedrohungen in Ihrer Umgebung zu überwachen. Azure Sentinel kann während des Vorschauzeitraums kostenlos verwendet werden. |         |![grünes Häkchen](../images/green-check-mark.png)|
|**Bereitstellen von [Azure ATP](https://docs.microsoft.com/en-us/azure-advanced-threat-protection/what-is-atp) ** zum Überwachen und schützen von Bedrohungen, die auf Ihre lokale Active Directory Umgebung zugeschnitten sind.   |         |![grünes Häkchen](../images/green-check-mark.png) |
|Verwenden Sie das **Azure-Sicherheits Center** , um Bedrohungen für Hybrid-und Cloud-Arbeitslasten zu überwachen. Das Azure-Sicherheits Center umfasst eine ﻿kostenlose Funktionsebene und eine Standardebene von Funktionen, die basierend auf Ressourcenstunden oder Transaktionen bezahlt werden.|         |         |

Das folgende Diagramm veranschaulicht diese Funktionen.
![Empfohlene Funktionen für kontinuierliche Überwachung und Überwachung](../images/m365-security-bdm-illustrations-monitoring-auditing.png)

Die wichtigsten empfohlenen Überwachungsaktionen:
- **Review Microsoft Secure Score Weekly** – Secure Score ist ein zentraler Ort, um auf den Sicherheitsstatus Ihres Office 365 Mandanten zuzugreifen und Aktionen basierend auf den wichtigsten Empfehlungen zu durchführen. Es wird empfohlen, diese Überprüfung wöchentlich durchzuführen. Secure Score enthält Empfehlungen aus Across Azure AD, InTune, Cloud App Security und Advanced Threat Protection von Microsoft Defender sowie Office 365. 
- **Wöchentliche Überprüfung riskanter Anmeldungen** – verwenden Sie das Azure AD Admin Center, um wöchentliche riskante Anmeldungen zu überprüfen. Der empfohlene Regelsatz für Identitäts-und Geräte Zugriff enthält eine Richtlinie zum Erzwingen der Kennwortänderung bei riskanten Anmeldungen.  
- **Wöchentliche Überprüfung der häufigsten Malware-und Phishing-Benutzer** – verwenden Sie Office Advanced Threat Protection Threat Explorer, um die wichtigsten Benutzer von Malware und Phishing zu überprüfen und die Ursache dafür zu ermitteln, warum diese Benutzer betroffen sind.
