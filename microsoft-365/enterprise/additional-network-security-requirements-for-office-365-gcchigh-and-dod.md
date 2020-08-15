---
title: Zusätzliche Netzwerksicherheitsanforderungen für Office 365 gcc High und DoD
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
description: 'Zusammenfassung: Office 365 gcc High und DoD bieten zusätzliche Netzwerksicherheitsanforderungen'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690575"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Zusätzliche Netzwerksicherheitsanforderungen für Office 365 gcc High und DoD

*Dieser Artikel bezieht sich auf Office 365 gcc High, Office 365 DoD, Microsoft 365 gcc High und Microsoft 365 DoD.*

Office 365 gcc High und DoD sind sichere Cloud-Umgebungen, die den Anforderungen der US-Regierung und ihrer Zulieferer und Auftragnehmer gerecht werden.  Diese Cloud-Umgebungen weisen zusätzliche Netzwerkeinschränkungen auf, auf welche externen Endpunkten die Dienste zugreifen dürfen.

GCC High-und DoD-Kunden, die die Verwendung von Verbundidentitäten oder hybrider Koexistenz planen, erfordern möglicherweise, dass Microsoft eingehende und/oder ausgehende Zugriffe auf Ihre vorhandenen lokalen Bereitstellungen zulässt.  Beispiele für diese Aktivitäten sind:

* Verwendung von Verbundidentitäten (mit Active Directory Verbunddiensten oder ähnlichen unterstützten STS)
* Hybride Koexistenz mit einer lokalen Exchange Server-oder Skype for Business-Bereitstellung
* Migration vorhandener Benutzer Inhalte aus einem lokalen System

Wenn Sie zulassen möchten, dass der Dienst mit Ihren lokalen Endpunkten kommuniziert, **müssen** Sie eine e-Mail an Office 365 Engineering für Netzwerkänderungen senden.

> [!WARNING]
> Alle Anforderungen haben eine **dreiwöchige** SLA und können aufgrund der erforderlichen Sicherheits-und Konformitätskontrollen und Bereitstellungs Pipelines nicht beschleunigt werden.  Dies umfasst die anfänglichen Onboarding-Netzwerkanforderungen sowie alle Änderungen, die nach dem Migrieren zu dem Dienst vorgenommen wurden.  Stellen Sie sicher, dass Ihre Netzwerkteams diese Zeitachse kennen und in Ihre Planungszyklen einbeziehen.

Senden Sie eine e-Mail an [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) mit den folgenden Informationen:

* **An**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)
* **Von**: ein mandantenadministrator-die Sende-e-Mail **muss** mit einem globalen Administratorkontakt in Ihrem Mandanten übereinstimmen.
* **E-Mail-Betreff**: Office 365 gcc High Network Request-contoso.onmicrosoft.US (ersetzen Sie dies durch ihren Mandantennamen)

Der Textkörper der Nachricht sollte die folgenden Daten enthalten:

* Ihr Microsoft Online Services-Mandantenname (dh contoso.onmicrosoft.com, fabrikam.onmicrosoft.US)
* Eine e-Mail-Verteilerliste, mit der Microsoft für die laufende Kommunikation im Zusammenhang mit Netzwerkänderungen und/oder der Nachverfolgung Ungültiger Subnetze kommuniziert
* Geben Sie an, ob Sie Microsoft Teams Hybrid Koexistenz mit Ihren lokalen Bereitstellungen verwenden möchten.
* Verbund Identitätssystem extern zugängliche URL (beispielsweise STS.contoso.com) und IP-Adressbereich in der CIDR-Notation (z.b. 10.1.1.0/28)
* Lokale PKI-Zertifikatsperrlisten-URL und IP-Adressbereich in der CIDR-Notation
* Extern zugängliche URL und IP-Adressbereich für Exchange Server lokale Bereitstellung in der CIDR-Notation
* Extern zugängliche URL und IP-Adressbereich für Skype for Business lokale Bereitstellung in der CIDR-Notation

Aus Sicherheits-und Kompatibilitätsgründen sollten Sie die folgenden Einschränkungen für Ihre Anforderung beachten:

* Es gibt eine Begrenzung für vier Subnetze pro Mandanten.
* Subnetze müssen sich in der CIDR-Notation befinden (z.b. 10.1.1.0/28)
* Subnetzbereiche dürfen nicht größer als/24 sein
* Wir **können keine** Anfragen für den Zugriff auf kommerzielle Cloud-Dienste (kommerzielle Office 365, Google G-Suite, Amazon-Webdienste usw.) erfüllen.

Nachdem Ihre Anfrage empfangen und von Microsoft genehmigt wurde, gibt es eine dreiwöchige SLA für die Implementierung und kann nicht beschleunigt werden.  Sie erhalten eine erste Bestätigung, wenn wir Ihre Anfrage und eine abschließende Bestätigung erhalten haben, nachdem Sie abgeschlossen wurde.
