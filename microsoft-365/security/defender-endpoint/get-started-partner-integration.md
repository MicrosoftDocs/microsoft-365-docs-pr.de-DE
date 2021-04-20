---
title: Werden Sie Microsoft Defender für Endpunkt-Partner
ms.reviewer: ''
description: Erfahren Sie mehr über die Schritte und Anforderungen, um Ihre Lösung in Microsoft Defender for Endpoint zu integrieren und Partner zu sein.
keywords: Partner, Integration, Lösungsüberprüfung, Zertifizierung, Anforderungen, Mitglied, Misa, Anwendungsportal
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 35ba1fe85fa9b62770142636d46303b37534b976
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893317"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Werden Sie Microsoft Defender für Endpunkt-Partner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Um ein Defender for Endpoint-Lösungspartner zu werden, müssen Sie die folgenden Schritte ausführen und ausführen.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Schritt 1: Abonnieren einer Microsoft Defender for Endpoint Developer-Lizenz
Abonnieren Sie die [Microsoft Defender for Endpoint Developer-Lizenz](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9). Mit dem Abonnieren können Sie einen Microsoft Defender for Endpoint-Mandanten mit bis zu 10 Geräten verwenden, um Lösungen zu entwickeln, die in Microsoft Defender for Endpoint integriert werden. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Schritt 2: Erfüllen der Anforderungen für die Validierung und Zertifizierung von Lösungen
Die beste Möglichkeit für Technologiepartner, zu bestätigen, dass ihre Integration funktioniert, besteht in  der Genehmigung des [](https://securitycenter.microsoft.com/interoperability/partners) vorgeschlagenen Integrationsentwurfs durch einen gemeinsamen Kunden (der Kunde kann die Option Partner empfehlen auf der Seite Partneranwendung im Microsoft Defender Security Center verwenden) und das Microsoft Defender for Endpoint-Team testen und demodieren lassen.

Sobald das Microsoft Defender for Endpoint-Team die Integration überprüft und genehmigt hat, werden wir Sie an die Microsoft Intelligent Security Association als Partner weiterver-

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Schritt 3: Mitglied der Microsoft Intelligent Security Association werden
[Microsoft Intelligent Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) ist ein Programm speziell für Microsoft-Sicherheitspartner, mit dem Sie Ihre Sicherheitsprodukte bereichern und die Kundenerkbarkeit Ihrer Integrationen in Microsoft-Sicherheitsprodukte verbessern können.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Schritt 4: Im Microsoft Defender for Endpoint-Partneranwendungsportal aufgelistet
Microsoft Defender for Endpoint unterstützt die Erkennung und Integration [](partner-applications.md) von Drittanbieteranwendungen mithilfe der Produktpartnerseite, die in das Microsoft Defender for Endpoint-Verwaltungsportal eingebettet ist. 

Damit Ihr Unternehmen als Partner auf der Produktpartnerseite aufgeführt wird, müssen Sie die folgenden Informationen bereitstellen:

1. Ein quadratisches Logo (SVG).
2. Name des zu präsentierten Produkts.
3. Geben Sie eine 15-Wort-Produktbeschreibung an.
4. Link zur Angebotsseite, damit der Kunde den Integrations- oder Blogbeitrag abschließen kann, der ausreichende Informationen für Kunden enthält. Jede Pressemitteilung, einschließlich des Microsoft Defender for Endpoint-Produktnamens, sollte von den Marketing- und Entwicklungsteams überprüft werden. Warten Sie mindestens 10 Tage, bis der Überprüfungsprozess durchgeführt wird.
5.  Wenn Sie einen azure AD-Ansatz mit mehreren Mandanten verwenden, benötigen wir den Azure AD-Anwendungsnamen, um die Verwendung der Anwendung nachverfolgt zu können.
6. Fügen Sie User-Agent-Feld in jeden API-Aufruf ein, der an öffentliche APIs oder Graph-Sicherheits-APIs an Microsoft Defender for Endpoint gesendet wird. Dies wird zu statistischen Zwecken, zur Problembehandlung und zur Partnererkennung verwendet. Darüber hinaus ist dieser Schritt eine Voraussetzung für die Mitgliedschaft in Microsoft Intelligent Security Association (MISA).

    Führen Sie die folgenden Schritte aus:
    
    - Legen Sie das User-Agent in jedem HTTP-Anforderungsheader auf das folgende Format.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Beispiel: User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Weitere Informationen finden Sie unter [RFC 2616 Section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Partnerschaften mit Microsoft Defender for Endpoint helfen unseren gemeinsamen Kunden, die Verteidigung weiter zu optimieren, zu integrieren und zu orchestrieren. Wir freuen uns, dass Sie sich entschieden haben, Microsoft Defender for Endpoint-Partner zu werden und unser gemeinsames Ziel zu erreichen, Kunden und ihre Ressourcen effektiv zu schützen, indem Sie moderne Bedrohungen gemeinsam verhindern und darauf reagieren.

## <a name="related-topics"></a>Verwandte Themen
- [Chancen für technische Partner](partner-integration.md)
