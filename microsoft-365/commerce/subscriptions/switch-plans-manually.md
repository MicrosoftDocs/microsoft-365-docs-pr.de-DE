---
title: Manueller Wechsel von Office 365 Business-Plänen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: eb0d0680-5677-41a0-8c46-4b9d47f1c209
ROBOTS: NOINDEX
description: Wechseln Sie Office 365 für Unternehmen Abonnements manuell, indem Sie ein neues Abonnement kaufen und sicherstellen, dass beide Abonnements aufgelistet und aktiv sind.
ms.openlocfilehash: 9a0c382abf1e61f1b31cb358529925053d037be4
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142103"
---
# <a name="switch-office-365-for-business-plans-manually"></a>Manueller Wechsel von Office 365 Business-Plänen

::: moniker range="o365-worldwide"

> [!NOTE]
> Dieser Artikel bezieht sich auf das alte Admin Center. Informationen zum Artikel über das neue Admin Center finden Sie unter [Ändern von Plänen manuell](change-plans-manually.md). Das neue Admin Center steht allen Microsoft 365-Administratoren zur Verfügung. Weitere Informationen lesen Sie unter [Informationen zum neuen Microsoft 365 Admin Center](../../admin/microsoft-365-admin-center-preview.md).

::: moniker-end

## <a name="step-1-decide-how-to-switch-plans"></a>Schritt 1: entscheiden, wie Pläne gewechselt werden sollen

Die beste Möglichkeit zum Umschalten aller Benutzer von einem Plan auf einen anderen besteht darin, die [Schaltfläche "Pläne wechseln"](switch-to-a-different-plan.md#use-the-switch-plans-button)zu verwenden. Manchmal ist dies nicht möglich. So können Sie den Umstieg manuell erledigen:
  
- Wenn die Schaltfläche **Pläne wechseln** nicht vorhanden ist.

- Wenn Sie die Schaltfläche **Pläne wechseln** auswählen, wird der gewünschte Plan nicht aufgeführt.

- Wenn Sie nicht alle Ihre Benutzer auf die gleiche Weise wechseln möchten. Bei einigen Unternehmen sollen unterschiedliche Benutzer unterschiedliche Pläne verwenden. Verwenden Sie hierfür den manuellen Wechsel.

Lesen Sie [Schritt 2: erwerben eines neuen Abonnements](#step-2-buy-a-new-subscription) in diesem Thema, um mit einem manuellen Switch fortzufahren.
  
## <a name="step-2-buy-a-new-subscription"></a>Schritt 2: erwerben eines neuen Abonnements

 **Abonnement bereits gekauft?** Wenn Sie bereits über ein Abonnement verfügen, auf das Sie Benutzer migrieren möchten, überspringen Sie diesen Schritt, und fahren Sie mit [Schritt 3: Überprüfen Ihres neuen Abonnements und der Lizenzen](#step-3-check-your-new-subscription-and-licenses) in diesem Thema fort.
  
- ODER -
  
 **Kaufen Sie ein neues Abonnement und die Lizenzen:** Folgen Sie den Schritten unter [Kaufen eines weiteren Office 365 Business-Abonnements](../buy-another-subscription.md) zum Erwerb eines neuen Abonnements.
  
Vergewissern Sie sich, dass Sie das Abonnement für dieselbe Organisation kaufen, in der sich die Benutzer jetzt befinden. Überprüfen Sie beispielsweise die e-Mail-Adressen der Benutzer, die Sie migrieren möchten. Wenn deren E-Mail-Adressen beispielsweise @contoso.com enthält, müssen Sie ein neues Abonnement für contoso.com kaufen. Schließen Sie eine Lizenz für jeden Benutzer ein, der auf den anderen Plan wechseln soll.
  
 **Wenn Sie Hilfe bei der Auswahl eines Plans benötigen**, finden Sie weitere Informationen unter [Office 365 für Unternehmen Produktvergleichs](https://go.microsoft.com/fwlink/p/?linkid=842056) Seite oder [unter Support für Anrufe](../../admin/contact-support-for-business-products.md).
  
## <a name="step-3-check-your-new-subscription-and-licenses"></a>Schritt 3: Überprüfen Ihres neuen Abonnements und der Lizenzen

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Abonnements</a>.

    Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.

    Wenn Sie Office 365, betrieben von 21Vianet verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.

2. **Sicherstellen, dass beide Abonnements aufgelistet und aktiv sind**

    Das Abonnement, von dem die Benutzer wechseln sollen, und das Abonnement, auf das die Benutzer umsteigen sollen, müssen zusammen aufgeführt werden. Wenn das neue Abonnement bei der ersten Überprüfung noch nicht aufgeführt wird, versuchen Sie es später noch einmal. Überprüfen Sie, dass beide Abonnements unter **AKTIV** aufgeführt werden. [Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv](#the-new-subscription-isnt-listed-or-isnt-active).

   **Das neue Office 365 Business-Abonnement mit verfügbaren Lizenzen**

    ![The subscription page showing the number of licenses for the new subscription.](../../media/65a73e96-7c95-4daa-b6ec-71a4bf74dda5.png)
  
3. **Überprüfen, dass ausreichend Lizenzen für jeden Benutzer bereitstehen**

    Jeder Benutzer benötigt eine Lizenz, die dem jeweiligen Abonnement entspricht. Wenn beispielsweise zehn Benutzer auf Office 365 Enterprise E5 umsteigen sollen, vergewissern Sie sich, dass Sie über zehn Lizenzen verfügen. In der hier angezeigten Abbildung wurden zehn Lizenzen für Office 365 Enterprise E5 erworben, und alle zehn Lizenzen können zugewiesen werden.

4. **Benötigen Sie weitere Lizenzen für das neue Abonnement?** Wechseln Sie zur Seite **Abonnements** , und [kaufen Sie Lizenzen für Ihr Office 365 für Unternehmen Abonnement](../licenses/buy-licenses.md).
  
    [Was passiert mit den alten Lizenzen?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv

- **Wenn Sie ein Abonnement auf Rechnung gekauft haben** und eine Bonitätsprüfung erforderlich ist, kann es bis zu zwei Arbeitstage dauern, bis das Abonnement verfügbar ist.

- **Wenn Sie zwei Abonnements gekauft haben und diese hier nicht aufgeführt werden**, wurden Sie möglicherweise für unterschiedliche Organisationen (für unterschiedliche Domänen) gekauft. Abonnements können nicht über Organisationsgrenzen hinweg eingesetzt werden.

- **Wenn Sie wissen, dass Sie ein zusätzliches Abonnement haben**und es hier nicht aufgeführt ist oder nicht unter **aktiv**aufgeführt ist, rufen Sie den [Support an](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Was passiert mit den alten Lizenzen?

Die Lizenzen aus dem aktuellen Abonnement werden später entfernt; Sie zahlen von da an also nur für die neuen Benutzerlizenzen.
  
## <a name="step-4-reassign-licenses"></a>Schritt 4: Lizenzen neu zuweisen

### <a name="reassign-a-license-for-one-user"></a>Neuzuweisen einer Lizenz für einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

    Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

    Wenn Sie Office 365, betrieben von 21Vianet verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Aktivieren Sie auf der Seite **Aktive Benutzer** das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.

3. Wählen Sie auf der rechten Seite in der Zeile **Produktlizenzen** die Option **Bearbeiten**aus.

4. Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten. Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen.

    > [!TIP]
    > Wenn Sie die für den Benutzer verfügbaren Dienste einschränken möchten, setzen Sie die Umschaltflächen für die Dienste, die Sie für diesen Benutzer entfernen möchten, auf die Stellung **Aus**. Soll der Benutzer beispielsweise Zugriff auf alle verfügbaren Dienste mit Ausnahme von Skype for Business Online haben, können Sie die Umschaltfläche für den Skype for Business Online-Dienst auf die Stellung **Aus** setzen.
  
    ![Setting license assignments for a user.](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
5. Wechseln Sie die Umschaltfläche für Lizenzen, die dieser Benutzer nicht mehr benötigt, in die Position **aus** .

6. Wählen Sie unten im Bereich **Produktlizenzen** die Option **Close** \> **Close** **zuweisen** \> aus.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Gleichzeitiges Neuzuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zur Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktive Benutzer</a> , oder wählen Sie **Benutzer** \> **aktive**Benutzer aus.

    Wenn Sie Office 365 Deutschland verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

    Wenn Sie Office 365, betrieben von 21Vianet verwenden, navigieren Sie zu dieser Seite <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie vorhandene Lizenzen ersetzen möchten.

3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.

4. Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.

5. Setzen Sie die Umschaltfläche für die Produkte, die Sie diesen Benutzern zuweisen möchten, auf die Stellung **Ein**.

    > [!TIP]
    > - Wenn Sie die für den Benutzer verfügbaren Dienste einschränken möchten, setzen Sie die Umschaltflächen für die Dienste, die Sie für diesen Benutzer entfernen möchten, auf die Stellung **Aus**. Soll der Benutzer beispielsweise Zugriff auf alle verfügbaren Dienste mit Ausnahme von Skype for Business Online haben, können Sie die Umschaltfläche für den Skype for Business Online-Dienst auf die Stellung **Aus** setzen.
    > - Alle vorherigen Lizenzzuweisungen für die ausgewählten Benutzer werden entfernt.
  
    ![Setting license assignments for a user.](../../media/5e53a979-6b08-4981-bb0b-fa657146334b.png)
  
6. Wählen Sie unten im Bereich **Vorhandene Produkte ersetzen** nacheinander **Ersetzen** \> **Schließen** aus.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Schritt 5: kündigen von Abonnements oder Entfernen von Lizenzen, die Sie nicht mehr benötigen (optional)

Wenn Sie alle Benutzer von einem Abonnement in das andere verschoben haben und Sie das ursprüngliche Abonnement nicht mehr benötigen, können Sie [das Abonnement kündigen](cancel-your-subscription.md).
  
Wenn Sie nur einige Benutzer in ein anderes Abonnement verschoben haben, können Sie die [Lizenzen entfernen](../licenses/remove-licenses-from-subscription.md), die Sie nicht mehr benötigen.
  
## <a name="call-support-to-help-you-switch-plans"></a>Anrufen des Supports, um Hilfe beim Wechseln von Plänen zu erhalten

[Rufen Sie den Support an.](../../admin/contact-support-for-business-products.md)