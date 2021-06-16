---
title: Zusätzliche Netzwerksicherheitsanforderungen für Office 365 GCC High und DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Zusammenfassung: Office 365 GCC High und DoD haben zusätzliche Netzwerksicherheitsanforderungen'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926559"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Zusätzliche Anforderungen an die Netzwerksicherheit für Office 365 GCC High und DOD

*Dieser Artikel bezieht sich auf Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High und Microsoft 365 DOD.*

Office 365 GCC High und DOD sind sichere Cloudumgebungen, die den Anforderungen der US-Regierung und ihrer Lieferanten und Auftragnehmer entsprechen.  Diese Cloudumgebungen haben zusätzliche Netzwerkeinschränkungen, auf die externe Endpunkte zugreifen dürfen, auf die die Dienste zugreifen dürfen.

GCC High- und DOD-Kunden, die Verbundidentitäten oder hybride Koexistenz planen, erfordern möglicherweise, dass Microsoft eingehenden und/oder ausgehenden Zugriff auf Ihre vorhandenen lokalen Bereitstellungen zulässt.  Beispiele für diese Aktivitäten sind:

* Verwendung von Verbundidentitäten (mit Active Directory-Verbunddiensten oder ähnlichen unterstützten STS)
* Hybrid koexistenz mit einer lokalen Exchange Server oder Skype for Business Bereitstellung
* Migration vorhandener Benutzerinhalte aus einem lokalen System

Damit der Dienst mit Ihren lokalen Endpunkten kommunizieren kann, **müssen** Sie eine E-Mail an Office 365 Engineering für Netzwerkänderungen senden.

> [!WARNING]
> Alle Anforderungen verfügen über eine **dreiwöchige** SLA und können aufgrund der erforderlichen Sicherheits- und Compliance-Kontrollen und Bereitstellungspipelines nicht beschleunigt werden.  Dies umfasst das anfängliche Onboarding von Netzwerkanforderungen sowie alle Änderungen nach der Migration zum Dienst.  Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen, und fügen Sie sie in ihre Planungszyklen ein.

Senden Sie eine E-Mail mit den folgenden Informationen an [Office 365 Government Allow-List Anforderungen:](mailto:o365gwlt@microsoft.com)

* **To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)
* **From**: A tenant administrator – the send email **must** match a Global Administrator contact in your tenant
* **E-Mail-Betreff:** Office 365 GCC High Network Request – contoso.onmicrosoft.us (ersetzen Sie durch Ihren Mandantennamen)

Der Nachrichtentext sollte die folgenden Daten enthalten:

* Ihr Microsoft Online Services-Mandantenname (z. B. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Eine E-Mail-Verteilerliste, mit der Microsoft für laufende Kommunikationen im Zusammenhang mit Netzwerkänderungen und/oder Nachverfolgung ungültiger Subnetze kommuniziert
* Geben Sie an, ob Sie Microsoft Teams hybride Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten.
* Url des Verbundidentitätssystems mit externem Zugriff (z. B. sts.contoso.com) und IP-Adressbereich in CIDR-Notation (z. B. 10.1.1.0/28)
* Url der lokalen PKI-Zertifikatsperrliste und IP-Adressbereich in CIDR-Notation
* URL und IP-Adressbereich für Exchange Server lokale Bereitstellung in CIDR-Notation
* URL und IP-Adressbereich für Skype for Business lokale Bereitstellung in CIDR-Notation

Beachten Sie aus Sicherheits- und Compliancegründen die folgenden Einschränkungen für Ihre Anforderung:

* Es gibt vier Subnetzeinschränkungen pro Mandant
* Subnetze müssen sich in CIDR-Notation befinden (z. B. 10.1.1.0/28)
* Subnetzbereiche dürfen nicht größer als /24
* Wir **können keine** Anforderungen erfüllen, um den Zugriff auf kommerzielle Clouddienste (kommerzielle Office 365, Google G-Suite, Amazon Web Services usw.) zuzulassen.

Sobald Ihre Anforderung von Microsoft empfangen und genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.  Sie erhalten eine anfängliche Bestätigung, wenn wir Ihre Anforderung erhalten haben, und eine endgültige Bestätigung, sobald sie abgeschlossen ist.
