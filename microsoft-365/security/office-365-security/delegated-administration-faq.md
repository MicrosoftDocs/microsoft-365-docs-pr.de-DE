---
title: Häufig gestellte Fragen zur delegierten Verwaltung
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: Dieses Thema liefert häufig gestellte Fragen und Antworten für Microsoft-Partner und Wiederverkäufer, die delegierte Office 365-Verwaltungsaufgaben ausführen möchten, einschließlich der Verwaltung von Exchange Online Protection (EOP) für andere Mandanten (Unternehmen).
ms.openlocfilehash: 2a237da685ae3c3d81c5a0912e15b5e7370e2118
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599482"
---
# <a name="delegated-administration-faq"></a>Häufig gestellte Fragen zur delegierten Verwaltung

Dieses Thema liefert häufig gestellte Fragen und Antworten für Microsoft-Partner und Wiederverkäufer, die delegierte Office 365-Verwaltungsaufgaben ausführen möchten, einschließlich der Verwaltung von Exchange Online Protection (EOP) für andere Mandanten (Unternehmen).

**F. Ich bin Wiederverkäufer und muss die Mandanten meines Kunden verwalten. Wie funktioniert das?**

A: Wenn Sie ein Microsoft-Partner oder-Wiederverkäufer sind und sich als Microsoft Advisor angemeldet haben, können Sie die Berechtigung zum Verwalten des Mandanten im Admin Center anfordern. Dies wird als delegierte Administration bezeichnet und ermöglicht Ihnen die Verwaltung des Office 365-Mandanten (einschließlich EOP-Einstellungen), als wären Sie ein Administrator in ihrer Organisation. Die Schritte für die delegierte Verwaltung sind wie folgt:

1. Registrieren Sie sich als [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrieren Sie sich für die delegierte Verwaltung in Office 365. Bevor Sie mit der Verwaltung eines Kundenkontos beginnen können, muss der Kunde Sie als delegierten Administrator autorisieren. Um die Genehmigung des Kunden einzuholen, [senden Sie ihm zuerst ein Angebot für die delegierte Verwaltung](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (Sie können Ihrem Kunden die delegierte Verwaltung auch später anbieten.)

3. Erstellen Sie das Delegierte Administratorkonto mithilfe der Schritte unter [hinzufügen, ändern oder Löschen eines Subscription Advisor-Partners](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visit [Partners: Erstellen Sie Ihr Unternehmen, und verwalten Sie Ihr Office 365 Partner Abonnement](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) , um weitere Informationen zum Einrichten Office 365 Delegierter Verwaltung zu erhalten.

**F. Ich bin Kunde und kein Wiederverkäufer. Wie kann ich mich als delegierten Administrator für meine Untermandanten einrichten?**

A. Die delegierte Verwaltung ist derzeit nur für Wiederverkäufer und Partner verfügbar. Wir haben jedoch ein Beispielskript für Windows PowerShell bereitgestellt, mit dessen Hilfe Sie Richtlinie auf Ihre Untermandanten (Unternehmen) anwenden können. Weitere Informationen finden Sie unter [Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**F. Kann ich verhindern, dass der Administrator für meine Untermandanten meine Richtlinie ändert?**

A. Office 365 unterstützt diese Funktion derzeit nicht.

**F. Ist eine konsolidierte Berichterstellung über meine Untermandanten hinweg möglich?**

A. Die konsolidierte Berichterstellung über die Unternehmen, die Sie verwalten, steht derzeit nicht für die Microsoft 365 Admin Center-Berichte zur Verfügung. Sie können dies jedoch mithilfe von [Microsoft Graph](https://docs.microsoft.com/graph/overview)tun.
