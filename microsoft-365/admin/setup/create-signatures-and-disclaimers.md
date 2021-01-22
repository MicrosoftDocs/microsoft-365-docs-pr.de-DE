---
title: Erstellen von organisationsweiten Signaturen und Haftungsausschlüssen
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Erfahren Sie, wie Sie E-Mail-Signaturen verwalten, einschließlich rechtlicher Haftungsausschlüsse oder Offenlegungserklärungen für alle E-Mail-Nachrichten, die in Ihre Organisation ein- oder aus ihrer Organisation gehen.
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926918"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Erstellen von organisationsweiten Signaturen und Haftungsausschlüssen

 Sie können E-Mail-Signaturen verwalten, indem Sie eine E-Mail-Signatur, einen Haftungsausschluss oder eine Offenlegungserklärung zu den E-Mail-Nachrichten hinzufügen, die in Ihre Organisation ein- oder austritten. Sie können sie so einrichten, dass sie auf alle eingehenden und ausgehenden Nachrichten angewendet wird, wie unten dargestellt. Sie können es auch auf bestimmte Nachrichten anwenden, z. B. nachrichten, die bestimmte Wörter oder Textmuster enthalten.

 Sehen Sie sich ein kurzes Video zum Erstellen einer unternehmensweiten E-Mail-Signatur an. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.

## <a name="create-a-signature-that-applies-to-all-messages"></a>Erstellen einer Signatur, die auf alle Nachrichten angewendet wird

> [!TIP]
> Organisationsweite Signaturen werden als "Haftungsausschlüsse" bezeichnet, unabhängig davon, was sie enthalten. Sie können z. B. nur eine Signatur sein oder auch Ihre Adresse, den Haftungsausschluss oder andere Informationen enthalten, die Sie wünschen.
    
::: moniker range="o365-worldwide"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Select the app launcher ![ The app launcher ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) icon, and then select **Admin**.
   
    Sie können die gesuchte App nicht finden? Wählen Sie im Startfeld der App alle **Apps** aus, um eine alphabetische Liste der verfügbaren Apps zu erhalten. Hier können Sie nach einer bestimmten App suchen. 
    
2. Wählen **Sie Admin Center** und dann Exchange **aus.**
    
3. Wählen Sie unter "Nachrichtenfluss" die **Option "Regeln" aus.**
    
4. Wählen Sie das **+** Symbol (Hinzufügen) und **Haftungsausschlüsse anwenden aus.**
    
5. Benennen Sie die Regel.
    
6. Wählen **Sie unter "Diese Regel anwenden"** **die Option [Auf alle Nachrichten anwenden] aus.**
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) zum Anwenden von Bedingungen, wenn der Haftungsausschluss nicht auf alle Nachrichten angewendet werden soll. (Dieser Artikel zum Thema Exchange Server gilt jedoch auch für Microsoft 365.) 
  
7. Lassen Sie unter "Folgendes ausführen" die Option **Haftungsausschluss anfügen** ausgewählt. 
    
8.  Wählen **Sie "Text eingeben"** aus, und geben Sie ihren Haftungsausschluss ein. 
    
    > [!TIP]
    > [Erfahren Sie mehr](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) zum Formatieren von Haftungsausschlüssen. (Dieser Formatierungsartikel ist für Exchange Server, gilt aber auch für Microsoft 365.) 

9. Wählen **Sie eine Option aus,** und wählen Sie **"Umbruch** als Ausweichoption" aus. Klicken Sie dann auf **OK**. Dies bedeutet: Wenn der Haftungsausschluss wegen Verschlüsselung oder einer anderen E-Mail-Einstellung nicht hinzugefügt werden kann, wird er in einen Nachrichtenumschlag eingeschlossen.
    
10. Lassen Sie **Diese Regel mit Schweregrad überwachen** aktiviert. Wählen Sie dann einen der Werte **Niedrig**, **Mittel** oder **Hoch** aus, der im Nachrichtenprotokoll verwendet werden soll. 
    
11. Wählen Sie **Erzwingen** aus, um den Haftungsausschluss sofort zu aktivieren, wenn Sie ihn nicht zuerst testen möchten. 
    
12. Wählen Sie **Weitere Optionen** aus, um zusätzliche Bedingungen oder Ausnahmen einzubeziehen. 
    
13. Wenn Sie fertig sind, wählen Sie **Speichern** aus. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Einschränkungen von organisationsweiten Signaturen

Folgende Schritte sind beim Verwalten von E-Mail-Signaturen in Microsoft 365 nicht verfügbar:
  
- Einfügen der Signatur direkt unter der neuesten E-Mail-Antwort oder Weiterleitung
    
- Anzeigen serverseitiger E-Mail-Signaturen in den Ordnern "Gesendete Elemente" von Benutzern
    
- Einbetten von Bildern in E-Mail-Signaturen
    
- Zeilen überspringen, die Variablen enthalten, die nicht aktualisiert werden konnten (z. B. weil der Wert nicht für einen Benutzer bereitgestellt wurde)
    
Um diese und andere Funktionen zum Verwalten von E-Mail-Signaturen zu erhalten, verwenden Sie ein Drittanbietertool. Bitte suchen Sie im Internet nach **E-Mail-Signatursoftware.** Eine Reihe dieser Anbieter sind Microsoft Gold Partner, und ihre Software bietet diese Funktionen. 
  
## <a name="more-resources"></a>Weitere Ressourcen

- Informationen zur Verwendung von PowerShell finden Sie unter Organisationsweite [Haftungsausschlüsse, Signaturen,](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) Fußzeilen oder Kopfzeilen in Exchange Online.