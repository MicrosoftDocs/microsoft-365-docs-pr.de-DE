---
title: Häufig gestellte Fragen zur delegierten Verwaltung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Administratoren können häufig gestellte Fragen und Antworten zu Delegierten Verwaltungsaufgaben in Microsoft 365 für Microsoft-Partner und-Händler anzeigen.
ms.openlocfilehash: 6729f276e6afea83568ca59d3bf48c08fcd837d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203143"
---
# <a name="delegated-administration-faq"></a>Häufig gestellte Fragen zur delegierten Verwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält häufig gestellte Fragen und Antworten zu Delegierten Verwaltungsaufgaben in Microsoft 365 für Microsoft-Partner und-Händler. Die delegierte Verwaltung umfasst die Möglichkeit zum Verwalten von Exchange Online Schutzeinstellungen (EoP) für andere Mandanten (Unternehmen).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Ich bin Händler und muss meine Kundenmandanten verwalten. Wie funktioniert das?

Wenn Sie ein Microsoft-Partner oder-Wiederverkäufer sind und sich als Microsoft Advisor angemeldet haben, können Sie _Delegierte Verwaltungs_ Funktionen in der Microsoft 365-Organisation Ihres Kunden anfordern.

Die delegierte Verwaltung ermöglicht Ihnen die Verwaltung von Microsoft 365 (einschließlich EoP-Einstellungen), als wären Sie ein Administrator in dieser Organisation. Die Schritte zum Konfigurieren der Delegierten Verwaltung werden in der folgenden Liste beschrieben:

1. Registrieren Sie sich als [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrieren Sie sich für die delegierte Verwaltung. Bevor Sie mit dem Verwalten des Mandanten eines Kunden beginnen können, müssen Sie Sie als Delegierter Administrator autorisieren. Um die Genehmigung des Kunden einzuholen, [senden Sie ihm zuerst ein Angebot für die delegierte Verwaltung](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Sie können Ihrem Kunden auch zu einem späteren Zeitpunkt eine delegierte Verwaltung anbieten.

3. Erstellen Sie das Delegierte Administratorkonto mithilfe der Schritte unter [hinzufügen, ändern oder Löschen eines Subscription Advisor-Partners](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Visit [Partners: Erstellen Sie Ihr Unternehmen, und verwalten Sie das Partner Abonnement](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) , um weitere Informationen zum Einrichten der Delegierten Verwaltung zu erhalten.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Ich bin Kunde, kein Reseller. Wie kann ich Delegierter Administrator für meine unter Mandanten einrichten?

Die delegierte Verwaltung ist nur für Wiederverkäufer und Partner verfügbar. Es gibt jedoch ein Beispiel-PowerShell-Skript, das Sie bei der Anwendung von Richtlinien auf Ihre unter Mandanten (Unternehmen) unterstützen wird. Weitere Informationen finden Sie unter [Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kann ich verhindern, dass mein unter mandantenadministrator meine Richtlinie ändert?

Nein. Microsoft 365 verfügt derzeit nicht über diese Funktion.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kann ich einen konsolidierten Bericht über alle meine unter Mandanten erhalten?

Die konsolidierte Berichterstellung in den von Ihnen verwalteten Unternehmen ist in Microsoft 365 Admin Center-Berichten nicht verfügbar. Sie können jedoch Berichte mithilfe von [Microsoft Graph](https://docs.microsoft.com/graph/overview)abrufen.
