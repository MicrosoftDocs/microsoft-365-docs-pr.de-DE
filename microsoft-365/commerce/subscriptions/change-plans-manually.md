---
title: Ändern Microsoft 365 für Geschäftspläne manuell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- MET150
ROBOTS: NOINDEX
description: Ändern Sie Abonnements manuell, indem Sie ein neues Abonnement kaufen und sicherstellen, dass die Abonnements aufgelistet und aktiv sind.
ms.date: 03/17/2021
ms.openlocfilehash: 7361b459e61961efbb729d80dcbb55dfdad65933
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293619"
---
# <a name="change-plans-manually"></a>Manuelles Ändern von Plänen

## <a name="step-1-decide-how-to-change-plans"></a>Schritt 1: Entscheiden, wie Pläne geändert werden

Die beste Möglichkeit, alle Ihre Benutzer von einem Plan in einen anderen zu ändern, ist die Verwendung [der Registerkarte Upgrade](upgrade-to-different-plan.md). Manchmal ist dies nicht möglich. Ändern Sie stattdessen Pläne manuell:

- Wenn die **Registerkarte Upgrade** angibt, dass Sie den aktuellen Plan nicht aktualisieren können.

- Wenn Sie die Registerkarte **Upgrade** auswählen, wird der von Ihnen ausgewählte Plan nicht aufgeführt.

- Wenn Sie nicht alle Benutzer auf die gleiche Weise aktualisieren möchten. Bei einigen Unternehmen sollen unterschiedliche Benutzer unterschiedliche Pläne verwenden. Verwenden Sie dazu eine manuelle Änderung.

Lesen Sie Schritt [2: Kaufen eines](#step-2-buy-a-new-subscription) neuen Abonnements in diesem Thema, um mit einer manuellen Änderung fortzufahren.

> [!IMPORTANT]
> Wenn Sie zu einem Plan mit weniger datenbezogenen Diensten wechseln als Ihr aktueller Plan (Downgrading), müssen Sie alle Daten, die Sie behalten möchten, manuell sichern. Weitere Informationen finden Sie unter [Sichern von Daten vor dem Ändern von Plänen.](back-up-data-before-switching-plans.md)

## <a name="step-2-buy-a-new-subscription"></a>Schritt 2: Kaufen eines neuen Abonnements

**Abonnement bereits gekauft?** Wenn Sie bereits über ein Abonnement verfügen, in das Sie Benutzer verschieben möchten, überspringen Sie diesen Schritt, und wechseln Sie zu [Schritt 3:](#step-3-check-your-new-subscription-and-licenses) Überprüfen Des neuen Abonnements und der Lizenzen in diesem Thema.

ODER

**Erwerben sie ein neues Abonnement und Lizenzen:** Führen Sie die Schritte unter [Buy another Microsoft 365 for business subscription](../try-or-buy-microsoft-365.md) to buy a new subscription aus.

Vergewissern Sie sich, dass Sie das Abonnement für dieselbe Organisation kaufen, in der sich die Benutzer jetzt befinden. Überprüfen Sie beispielsweise die E-Mail-Adressen für die Benutzer, die Sie verschieben möchten. Wenn ihre \@ E-Mail-Contoso.com enthalten, müssen Sie ein neues Abonnement für contoso.com.
Schließen Sie eine Lizenz für jeden Benutzer ein, der auf den anderen Plan wechseln soll.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Schritt 3: Überprüfen Ihres neuen Abonnements und Ihrer Lizenzen

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.

2. **Überprüfen, ob beide Abonnements aufgelistet und aktiv sind** Das Abonnement, aus dem Sie Benutzer verschieben, und das Abonnement, in das Sie Benutzer verschieben, müssen zusammen aufgeführt werden. Wenn das neue Abonnement bei der ersten Überprüfung noch nicht aufgeführt wird, versuchen Sie es später noch einmal. Überprüfen Sie, ob beide Abonnements aktiv sind. [Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Überprüfen, ob Sie über genügend Lizenzen für jeden Benutzer verfügen** Jeder Benutzer benötigt eine Lizenz, die dem Abonnement entspricht. Wenn Sie also zehn Benutzer in Microsoft 365 Business Premium verschieben möchten, müssen Sie sicherstellen, dass zehn Lizenzen verfügbar sind.

4. **Benötigen Sie weitere Lizenzen für das neue Abonnement?**
   Wechseln Sie zur **Seite Ihre Produkte,** und [erwerben Sie weitere Lizenzen.](../licenses/buy-licenses.md)

> [Was passiert mit den alten Lizenzen?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>Das neue Abonnement wird nicht aufgeführt oder ist nicht aktiv

- **Wenn Sie zwei Abonnements gekauft haben und diese hier nicht aufgeführt werden**, wurden Sie möglicherweise für unterschiedliche Organisationen (für unterschiedliche Domänen) gekauft. Abonnements können nicht über Organisationsgrenzen hinweg eingesetzt werden.

- **Wenn Sie wissen, dass Sie über ein zusätzliches** Abonnement verfügen und es hier nicht aufgeführt ist oder nicht aktiv ist, rufen Sie [den Microsoft-Support an.](../../business-video/get-help-support.md)

### <a name="what-about-the-old-licenses"></a>Was passiert mit den alten Lizenzen?

Die Lizenzen aus dem aktuellen Abonnement werden später entfernt; Sie zahlen von da an also nur für die neuen Benutzerlizenzen.

## <a name="step-4-reassign-licenses"></a>Schritt 4: Erneutes Zuweisen von Lizenzen

### <a name="reassign-a-license-for-one-user"></a>Neuzuweisen einer Lizenz für einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie **auf der** Seite Aktive Benutzer den Benutzer aus, dem Sie eine Lizenz zuweisen möchten.

3. Erweitern Sie **auf der** Registerkarte Lizenzen und Apps die Option **Lizenzen,** wählen Sie die Felder für die Lizenzen aus, die Sie zuweisen möchten, und wählen Sie **dann Änderungen speichern aus.**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Gleichzeitiges Neuzuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie vorhandene Lizenzen ersetzen möchten.

3. Wählen Sie oben weitere **Optionen** (**...**) aus, und wählen Sie dann **Produktlizenzen verwalten aus.**

4. Wählen Sie **Vorhandene Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.

5. Setzen Sie die Umschaltfläche für die Produkte, die Sie diesen Benutzern zuweisen möchten, auf die Stellung **Ein**.

    > [!TIP]
    > - Wenn Sie die für den Benutzer verfügbaren Dienste einschränken möchten, setzen Sie die Umschaltflächen für die Dienste, die Sie für diesen Benutzer entfernen möchten, auf die Stellung **Aus**. Soll der Benutzer beispielsweise Zugriff auf alle verfügbaren Dienste mit Ausnahme von Skype for Business Online haben, können Sie die Umschaltfläche für den Skype for Business Online-Dienst auf die Stellung **Aus** setzen.
    > - Alle vorherigen Lizenzzuweisungen für die ausgewählten Benutzer werden entfernt.

6. Wählen Sie unten im Bereich **Vorhandene Produkte ersetzen** nacheinander **Ersetzen** \> **Schließen** aus.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Schritt 5: Kündigen von Abonnements oder Entfernen von Lizenzen, die Sie nicht mehr benötigen (Optional)

Wenn Sie alle Benutzer von einem Abonnement in das andere verschoben haben und Sie das ursprüngliche Abonnement nicht mehr benötigen, können Sie [das Abonnement kündigen](cancel-your-subscription.md).

Wenn Sie nur einige Benutzer in ein anderes Abonnement verschoben haben, können Sie die [Lizenzen entfernen](../licenses/buy-licenses.md), die Sie nicht mehr benötigen.

## <a name="call-support-to-help-you-change-plans"></a>Rufen Sie den Support auf, um Ihnen beim Ändern von Plänen zu helfen
[Rufen Sie den Microsoft-Support an](../../business-video/get-help-support.md)