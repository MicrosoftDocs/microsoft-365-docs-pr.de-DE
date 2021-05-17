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
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690575"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Zusätzliche Anforderungen an die Netzwerksicherheit für Office 365 GCC High und DOD

*Dieser Artikel gilt für Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High und Microsoft 365 DOD.*

Office 365 GCC High und DOD sind sichere Cloudumgebungen, die den Anforderungen der US-Regierung und ihrer Lieferanten und Auftragnehmer entsprechen.  Diese Cloudumgebungen verfügen über zusätzliche Netzwerkeinschränkungen, auf die externe Endpunkte zugreifen dürfen, auf die die Dienste zugreifen dürfen.

GCC Kunden mit hoher Und-DoD-Anzahl, die Verbundidentitäten oder hybride Koexistenz verwenden möchten, müssen möglicherweise von Microsoft eingehenden und/oder ausgehenden Zugriff auf Ihre vorhandenen lokalen Bereitstellungen zulassen.  Beispiele für diese Aktivitäten sind:

* Verwendung von Verbundidentitäten (mit Active Directory Federation Services oder ähnlichen unterstützten STS)
* Hybride Koexistenz mit einer lokalen Exchange Server oder Skype for Business Bereitstellung
* Migration vorhandener Benutzerinhalte aus einem lokalen System

Damit der Dienst mit Ihren lokalen Endpunkten  kommunizieren kann, müssen Sie eine E-Mail an Office 365 für Netzwerkänderungen senden.

> [!WARNING]
> Alle Anforderungen verfügen über eine SLA **von** drei Wochen und können aufgrund der erforderlichen Sicherheits- und Compliancekontrollen und Bereitstellungspipelines nicht beschleunigt werden.  Dies umfasst anfängliche Onboardingnetzwerkanforderungen sowie alle Änderungen nach der Migration zum Dienst.  Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen und in ihre Planungszyklen einfügen.

Senden Sie eine E-Mail [an Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) mit den folgenden Informationen:

* **To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)
* **From**: A tenant administrator – the send email **must match** a Global Administrator contact in your tenant
* **E-Mail-Betreff**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (ersetzen Sie dies durch Ihren Mandantennamen)

Der Nachrichtentext sollte die folgenden Daten enthalten:

* Ihr Microsoft Online Services Mandantenname (d. h. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Eine E-Mail-Verteilerliste, mit der Microsoft für die aktuelle Kommunikation im Zusammenhang mit Netzwerkänderungen und/oder der Nachverteiler für ungültige Subnetze kommuniziert
* Geben Sie an, ob Sie Microsoft Teams hybride Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten
* Extern zugängliche URL des Verbundidentitätssystems (z. B. sts.contoso.com) und IP-Adressbereich in CIDR-Notation (z. B. 10.1.1.0/28)
* Lokale PKI-Zertifikatsperrlisten-URL und IP-Adressbereich in CIDR-Notation
* Extern zugänglicher URL- und IP-Adressbereich für Exchange Server lokale Bereitstellung in CIDR-Notation
* Extern zugänglicher URL- und IP-Adressbereich für Skype for Business lokale Bereitstellung in CIDR-Notation

Beachten Sie aus Sicherheits- und Compliancegründen die folgenden Einschränkungen für Ihre Anforderung:

* Es gibt eine Vier-Subnetz-Beschränkung pro Mandant
* Subnetze müssen sich in CIDR Notation befinden (z. B. 10.1.1.0/28)
* Subnetzbereiche dürfen nicht größer als /24
* Wir **können Anforderungen** zum Zulassen des Zugriffs auf kommerzielle Clouddienste (kommerzielle Office 365, Google G-Suite, Amazon Web Services usw.) nicht erfüllen.

Sobald Ihre Anforderung von Microsoft empfangen und genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.  Sie erhalten eine erste Bestätigung, wenn wir Ihre Anforderung erhalten haben, und eine endgültige Bestätigung, nachdem sie abgeschlossen wurde.
