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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Administratoren können häufig gestellte Fragen und Antworten zu delegierten Verwaltungsaufgaben in Microsoft 365 für Microsoft-Partner und -Händler anzeigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205951"
---
# <a name="delegated-administration-faq"></a>Häufig gestellte Fragen zur delegierten Verwaltung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Dieser Artikel enthält häufig gestellte Fragen und Antworten zu delegierten Verwaltungsaufgaben in Microsoft 365 für Microsoft-Partner und -Händler. Die delegierte Verwaltung umfasst die Möglichkeit, Exchange Online Protection (EOP)-Einstellungen für andere Mandanten (Unternehmen) zu verwalten.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Ich bin Vertriebspartner und muss meine Kunden mandanten verwalten. Wie funktioniert das?

Wenn Sie ein Microsoft-Partner oder -Vertriebspartner sind und sich als Microsoft-Berater angemeldet haben, können Sie delegierte Verwaltungsfunktionen in der Microsoft 365-Organisation Ihres Kunden anfordern. 

Mit der delegierten Verwaltung können Sie Microsoft 365 (einschließlich EOP-Einstellungen) verwalten, als wären Sie ein Administrator in dieser Organisation. Die Schritte zum Konfigurieren der delegierten Verwaltung werden in der folgenden Liste beschrieben:

1. Registrieren Sie sich als [Microsoft Office 365 Advisor](https://partner.microsoft.com/?cloudbenefits).

2. Registrieren Sie sich für delegierte Verwaltung. Bevor Sie mit der Verwaltung des Mandanten eines Kunden beginnen können, müssen sie Sie als delegierter Administrator autorisieren. Um die Genehmigung des Kunden einzuholen, [senden Sie ihm zuerst ein Angebot für die delegierte Verwaltung](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Sie können Ihren Kunden auch zu einem späteren Zeitpunkt eine delegierte Verwaltung anbieten.

3. Erstellen Sie das delegierte Administratorkonto mithilfe der Schritte unter Hinzufügen, Ändern oder [Löschen eines Abonnementberaterpartners.](../../admin/misc/add-partner.md)

Besuchen [Sie Partner: Erstellen Sie Ihr Geschäfts- und Verwaltungspartnerabonnement,](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) um weitere Informationen zum Einrichten einer delegierten Verwaltung zu erhalten.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Ich bin Ein Kunde, kein Händler. Wie kann ein delegierter Administrator für meine Untertenanten eingerichtet werden?

Delegierte Verwaltung ist nur für Händler und Partner verfügbar. Es gibt jedoch ein PowerShell-Beispielskript, mit dem Sie Richtlinien auf Ihre Untertenanten (Unternehmen) anwenden können. Weitere Informationen finden Sie unter [Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kann ich verhindern, dass mein Untergeordneter Administrator meine Richtlinie ändert?

Nein. Microsoft 365 verfügt derzeit nicht über diese Funktion.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kann ich eine konsolidierte Berichterstellung für alle meine Untertenanten erhalten?

Konsolidierte Berichte in den von Ihnen verwalteten Unternehmen sind in Microsoft 365 Admin Center-Berichten nicht verfügbar. Sie können jedoch Berichte mithilfe von [Microsoft Graph erhalten.](/graph/overview)