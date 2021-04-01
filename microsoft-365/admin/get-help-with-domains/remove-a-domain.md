---
title: Entfernen einer Domäne
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Erfahren Sie, wie Sie eine alte Domäne aus Microsoft 365 entfernen und Benutzer und Gruppen in eine andere Domäne verschieben.
ms.openlocfilehash: 916730975e9e17c42b01d9fa0ff55b3cb7078f66
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470965"
---
# <a name="remove-a-domain"></a>Entfernen einer Domäne
  
 **[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen. 
  
Entfernen Sie Ihre Domäne, weil Sie sie einem anderen Microsoft 365-Abonnementplan hinzufügen möchten? Oder möchten Sie Ihr Abonnement einfach nur kündigen? Sie können [Ihren Plan oder Ihr Abonnement ändern](../../commerce/subscriptions/switch-to-a-different-plan.md) oder [Ihr Abonnement kündigen](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Schritt 1: Verschieben von Benutzern in eine andere Domäne

#### <a name="move-users"></a>Verschieben von Benutzern

::: moniker range="o365-worldwide"

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>.

2. Wählen Sie **Benutzer** > **Aktive Benutzer aus.**

3. Wählen Sie die Felder neben den Namen aller Benutzer aus, die Sie verschieben möchten.

4. Wählen **Sie weitere Optionen** (**...**), oben auf der Seite aus, und wählen Sie dann Domänen **ändern aus.**

5. Wählen Sie **im Bereich** Domänen ändern eine andere Domäne aus.

Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>.  

2. Wählen Sie **Benutzer** > **Aktive Benutzer aus.**

3. Wählen Sie die Felder neben den Namen aller Benutzer aus, die Sie verschieben möchten.

4. Wählen Sie oben auf  der Seite weitere > **Domänen bearbeiten aus.**

5. Wählen Sie **im Bereich** Domänen bearbeiten eine andere Domäne aus.
  
Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.  

2. Wählen Sie **Benutzer** > **Aktive Benutzer aus.**

3. Wählen Sie die Felder neben den Namen aller Benutzer aus, die Sie verschieben möchten.

4. Wählen Sie oben auf  der Seite weitere > **Domänen bearbeiten aus.**

5. Wählen Sie **im Bereich** Domänen bearbeiten eine andere Domäne aus.
  
Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.

::: moniker-end

#### <a name="move-yourself"></a>Verschieben Sie sich selbst

::: moniker range="o365-worldwide"

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.

2. Wechseln Sie **zu** \> **Aktive Benutzer**, und wählen Sie Ihr Konto aus der Liste aus.

3. Wählen Sie **auf der Registerkarte** Konto die Option **Benutzername** verwalten aus, und wählen Sie dann eine andere Domäne aus.
  
4. Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **dann Abmelden aus.**

5. Melden Sie sich mit der neuen Domäne und demselben Kennwort an.

Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie **zu Aktive** \> **Benutzer**, und wählen Sie Ihren Namen in der Liste aus.

2. Wählen Sie **im Abschnitt Benutzername/E-Mail** die Option **Bearbeiten** aus, und wählen Sie dann eine andere Domäne aus.

3. Wählen **Sie Set as primary** > **Save** Close > **aus.**
  
4. Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **dann Abmelden aus.**

5. Melden Sie sich mit der neuen Domäne und demselben Kennwort an.

Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie **zu Aktive** \> **Benutzer**, und wählen Sie Ihren Namen in der Liste aus.

2. Wählen Sie **im Abschnitt Benutzername/E-Mail** die Option **Bearbeiten** aus, und wählen Sie dann eine andere Domäne aus.

3. Wählen **Sie Set as primary** > **Save** Close > **aus.**
  
4. Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **dann Abmelden aus.**

5. Melden Sie sich mit der neuen Domäne und demselben Kennwort an.

Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Schritt 2: Verschieben von Gruppen in eine andere Domäne

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.
  
2. Wählen Sie den Gruppennamen aus, und wählen Sie dann auf der Registerkarte **Allgemein** unter **E-Mail-Adresse, Primär,** **Bearbeiten aus.**

3. Verwenden Sie die Dropdownliste, um eine andere Domäne zu wählen.

4. Wählen Sie **Speichern** und dann **Schließen** aus. Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite  > **Gruppengruppen.**

2. Wählen Sie den Gruppennamen aus, und wählen Sie dann **Bearbeiten neben** **Name aus.**

3. Verwenden Sie die Dropdownliste, um eine andere Domäne zu wählen.

4. Wählen Sie **Speichern** und dann **Schließen** aus. Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite  > **Gruppengruppen.**

2. Wählen Sie den Gruppennamen aus, und wählen Sie dann **Bearbeiten neben** **Name aus.**

3. Verwenden Sie die Dropdownliste, um eine andere Domäne zu wählen.

4. Wählen Sie **Speichern** und dann **Schließen** aus. Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Schritt 3: Entfernen der alten Domäne

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setupdomänen.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin  Center zur Seite \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setupdomänen.</a>

::: moniker-end
  
2. Wählen Sie **auf** der Seite Domänen die Domäne aus, die Sie entfernen möchten.

3. Wählen Sie im rechten Bereich **Entfernen aus.**

4. Folgen Sie allen zusätzlichen Eingabeaufforderungen, und wählen Sie dann **Schließen aus.**

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Wie lange dauert es, bis eine Domäne entfernt wurde?

Es kann bis zu 5 Minuten dauern, bis Microsoft 365 eine Domäne entfernt, wenn an vielen Stellen wie Sicherheitsgruppen, Verteilerlisten, Benutzern und Microsoft 365-Gruppen nicht auf sie verwiesen wird. Wenn es viele Verweise gibt, die die Domäne verwenden, kann es mehrere Stunden (pro Tag) dauern, bis die Domäne entfernt wird.
  
Wenn Sie über Hunderte oder Tausende von Benutzern verfügen, verwenden Sie PowerShell, um alle Benutzer abzufragen und in eine andere Domäne zu verschieben. Andernfalls könnte es passieren, dass einige Benutzer der Benutzeroberfläche vergessen werden. Wenn dann das Entfernen der Domäne nicht möglich ist, wissen Sie nicht, warum. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Benötigen Sie weitere Hilfe?

::: moniker range="o365-worldwide"

> [!NOTE]
> Sie können die [".onmicrosoft.com"](../setup/domains-faq.yml)-Domäne nicht aus Ihrem Konto entfernen. Wenn Sie eine Domäne entfernen, werden Benutzerkonten wieder zur Adresse ".onmicrosoft.com" als primärer SMTP/UserprincipalName zurückgesetzt.
  
Funktioniert es immer noch nicht? Die Domäne muss möglicherweise manuell entfernt werden. [Rufen Sie uns an](../contact-support-for-business-products.md), und wir helfen Ihnen bei der Problemlösung!
  
::: moniker-end

## <a name="related-articles"></a>Verwandte Artikel

[Häufig gestellte Fragen zu Domänen](../setup/domains-faq.yml)

[Wechseln zu einem anderen Microsoft 365 Business-Plan](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Kündigen Ihres Abonnements](../../commerce/subscriptions/cancel-your-subscription.md)