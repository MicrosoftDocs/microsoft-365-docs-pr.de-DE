---
title: Verwalten von Lizenzen für Geräte
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Hier erfahren Sie, wie Sie Gruppen für die Verwendung mit Geräten Lizenzen zuweisen.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638183"
---
# <a name="manage-licenses-for-devices"></a>Verwalten von Lizenzen für Geräte

Wenn Sie Microsoft 365 Apps für Unternehmen (Gerät) oder Microsoft 365 Apps für Bildungseinrichtungen (Gerät) haben, können Sie Geräte mithilfe Azure AD Gruppenlizenzen zuweisen. Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Microsoft 365-Apps für Enterprise (zuvor mit dem Namen Office 365 ProPlus) verwenden. Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden. Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Microsoft 365-Apps für Enterprise, ohne dass eine eigene Lizenz erforderlich ist.

> [!IMPORTANT]
> Die gerätebasierte Lizenzierung für Microsoft 365-Apps für Unternehmen ist nur als Add-on-Lizenz für einige kommerzielle Kunden und einige Schulungs Kunden verfügbar. Für kommerzielle Kunden ist die Lizenz *Microsoft 365 apps for Enterprise (Gerät)* und steht nur über Enterprise Agreement/Enterprise Agreement Subscription zur Verfügung. Für Education-Kunden ist die Lizenz *Microsoft 365 apps for Education (Gerät)* und ist nur über die Registrierung für Bildungslösungen (EBS) verfügbar. Weitere Informationen finden Sie im Blogbeitrag zur [Verfügbarkeit von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Wenden Sie sich für kommerzielle Verfügbarkeit an Ihren Microsoft-Konto Vertreter.

Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen dann der Gruppe Geräte zu. Weitere Informationen zur Geräte Lizenzierung, einschließlich Geräteanforderungen, zu den Arten von Gruppen, die Sie verwenden können, und zum Konfigurieren von Microsoft 365-Apps für Enterprise zur Verwendung der Geräte Lizenzierung finden Sie unter [Device-based licensing for Microsoft 365 apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.

## <a name="assign-licenses-to-devices"></a>Zuweisen von Lizenzen zu Geräten

Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu. Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie auf der Seite **Lizenzen** die Option **Microsoft 365 apps for Education (Gerät)** oder **Microsoft 365 apps for Enterprise (Gerät)** aus.
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen**aus.
4. Geben Sie im Bereich **Lizenzen einer Gruppe zuweisen** die Eingabe eines Gruppennamens ein, und wählen Sie ihn aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.
5. Wählen Sie **assign**und dann **Close**aus.

## <a name="unassign-licenses-from-devices"></a>Aufheben der Zuweisung von Lizenzen von Geräten

Wenn Sie die Zuweisung von Lizenzen von einer Gruppe aufheben, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe. Alle apps und die zugehörigen Daten sind dann schreibgeschützt.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie auf der Seite **Lizenzen** die Option **Microsoft 365 apps for Education (Gerät)** oder **Microsoft 365 apps for Enterprise (Gerät)** aus.
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie **Weitere Aktionen**aus, und wählen Sie dann Lizenzen für die **Zuweisung**aufheben aus.
4. Wählen Sie im Dialogfeld **Lizenzen** aufheben die Option **Zuweisung**aufheben aus.