---
title: Manuelles Ändern von Microsoft 365 for Business-Plänen
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
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Ändern Sie Abonnements manuell, indem Sie ein neues Abonnement kaufen und sicherstellen, dass beide Abonnements aufgelistet und aktiv sind.
ms.openlocfilehash: bcd9a129ef1597469ef9bbf93841b5db4f919f1e
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43707631"
---
# <a name="change-plans-manually"></a>Manuelles Ändern von Plänen

## <a name="step-1-decide-how-to-change-plans"></a>Schritt 1: entscheiden, wie Pläne geändert werden

Die beste Möglichkeit, alle Ihre Benutzer von einem Plan in einen anderen zu ändern, ist [die Verwendung der Registerkarte "Upgrade"](upgrade-to-different-plan.md). Manchmal ist dies nicht möglich. Stattdessen werden Pläne manuell geändert:

- Wenn die Registerkarte **Upgrade** anzeigt, dass der aktuelle Plan nicht aktualisiert werden kann.

- Wenn Sie die Registerkarte **Upgrade** auswählen, wird der gewünschte Plan nicht aufgeführt.

- Wenn Sie nicht alle Ihre Benutzer auf die gleiche Weise aktualisieren möchten. Bei einigen Unternehmen sollen unterschiedliche Benutzer unterschiedliche Pläne verwenden. Verwenden Sie hierfür eine manuelle Änderung.

Lesen Sie [Schritt 2: erwerben eines neuen Abonnements](#step-2-buy-a-new-subscription) in diesem Thema, um mit einer manuellen Änderung fortzufahren.

> [!IMPORTANT]
> Wenn Sie zu einem Plan mit weniger datenbezogenen Diensten wechseln als Ihr aktueller Plan (Herabstufung), müssen Sie alle Daten, die Sie behalten möchten, manuell sichern. Weitere Informationen finden Sie unter [Sichern von Daten vor dem Ändern von Plänen](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Schritt 2: erwerben eines neuen Abonnements

**Abonnement bereits gekauft?** Wenn Sie bereits über ein Abonnement verfügen, auf das Sie Benutzer migrieren möchten, überspringen Sie diesen Schritt, und fahren Sie mit [Schritt 3: Überprüfen Ihres neuen Abonnements und der Lizenzen](#step-3-check-your-new-subscription-and-licenses) in diesem Thema fort.

ODER

**Erwerben Sie ein neues Abonnement und Lizenzen:** Befolgen Sie die Schritte unter [kaufen eines anderen Microsoft 365 for Business-Abonnements](../buy-another-subscription.md) , um ein neues Abonnement zu erwerben.

Vergewissern Sie sich, dass Sie das Abonnement für dieselbe Organisation kaufen, in der sich die Benutzer jetzt befinden. Überprüfen Sie beispielsweise die e-Mail-Adressen der Benutzer, die Sie migrieren möchten. Wenn Ihre e-Mail \@-Adressen contoso.com enthalten, müssen Sie ein neues Abonnement für contoso.com erwerben.
Schließen Sie eine Lizenz für jeden Benutzer ein, der auf den anderen Plan wechseln soll.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Schritt 3: Überprüfen Ihres neuen Abonnements und der Lizenzen

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte und Dienste</a>.

2. **Sicherstellen, dass beide Abonnements aufgelistet und aktiv sind** Das Abonnement, aus dem Sie Benutzer verschieben, und das Abonnement, auf das Sie Benutzer verschieben, müssen zusammen aufgeführt werden. Wenn das neue Abonnement bei der ersten Überprüfung noch nicht aufgeführt wird, versuchen Sie es später noch einmal. Stellen Sie sicher, dass beide Abonnements aktiv sind. [Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv](#the-new-subscription-isnt-listed-or-isnt-active).

3. Stellen **Sie sicher, dass für jeden Benutzer genügend Lizenzen vorhanden sind** . Jeder Benutzer benötigt eine Lizenz, die seinem Abonnement entspricht. Wenn Sie also zehn Benutzer zu Microsoft 365 Business Premium migrieren möchten, müssen Sie sicherstellen, dass zehn Lizenzen verfügbar sind.

4. **Benötigen Sie weitere Lizenzen für das neue Abonnement?**
   Wechseln Sie zur Seite **Produkte & Dienste** , und [kaufen Sie weitere Lizenzen](../licenses/buy-licenses.md).

> [Was passiert mit den alten Lizenzen?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv

- **Wenn Sie zwei Abonnements gekauft haben und diese hier nicht aufgeführt werden**, wurden Sie möglicherweise für unterschiedliche Organisationen (für unterschiedliche Domänen) gekauft. Abonnements können nicht über Organisationsgrenzen hinweg eingesetzt werden.

- **Wenn Sie wissen, dass Sie ein zusätzliches Abonnement haben**und es hier nicht aufgeführt ist oder nicht aktiv ist, [rufen Sie den Microsoft-Support an](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>Was passiert mit den alten Lizenzen?

Die Lizenzen aus dem aktuellen Abonnement werden später entfernt; Sie zahlen von da an also nur für die neuen Benutzerlizenzen.

## <a name="step-4-reassign-licenses"></a>Schritt 4: Lizenzen neu zuweisen

### <a name="reassign-a-license-for-one-user"></a>Neuzuweisen einer Lizenz für einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie auf der Seite **aktive Benutzer** den Benutzer aus, dem Sie eine Lizenz zuweisen möchten.

3. Erweitern Sie auf der Registerkarte te **Lizenzen und apps** die Option **Lizenzen**, wählen Sie die Felder für die Lizenzen aus, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern**aus.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Gleichzeitiges Neuzuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie vorhandene Lizenzen ersetzen möchten.

3. Wählen Sie im oberen Bereich **Weitere Optionen** (**...**) aus, und wählen Sie dann **Produktlizenzen verwalten**aus.

4. Wählen Sie **Vorhandene Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.

5. Setzen Sie die Umschaltfläche für die Produkte, die Sie diesen Benutzern zuweisen möchten, auf die Stellung **Ein**.

    > [!TIP]
    > - Wenn Sie die für den Benutzer verfügbaren Dienste einschränken möchten, setzen Sie die Umschaltflächen für die Dienste, die Sie für diesen Benutzer entfernen möchten, auf die Stellung **Aus**. Soll der Benutzer beispielsweise Zugriff auf alle verfügbaren Dienste mit Ausnahme von Skype for Business Online haben, können Sie die Umschaltfläche für den Skype for Business Online-Dienst auf die Stellung **Aus** setzen.
    > - Alle vorherigen Lizenzzuweisungen für die ausgewählten Benutzer werden entfernt.

6. Wählen Sie unten im Bereich **Vorhandene Produkte ersetzen** nacheinander **Ersetzen** \> **Schließen** aus.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Schritt 5: kündigen von Abonnements oder Entfernen von Lizenzen, die Sie nicht mehr benötigen (optional)

Wenn Sie alle Benutzer von einem Abonnement in das andere verschoben haben und Sie das ursprüngliche Abonnement nicht mehr benötigen, können Sie [das Abonnement kündigen](cancel-your-subscription.md).

Wenn Sie nur einige Benutzer in ein anderes Abonnement verschoben haben, können Sie die [Lizenzen entfernen](../licenses/remove-licenses-from-subscription.md), die Sie nicht mehr benötigen.

## <a name="call-support-to-help-you-change-plans"></a>Unterstützung bei der Anruf Unterstützung beim Ändern der Pläne
[Anrufen des Microsoft-Supports](../../admin/contact-support-for-business-products.md)