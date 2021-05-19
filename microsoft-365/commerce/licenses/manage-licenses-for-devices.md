---
title: Verwalten von Lizenzen für Geräte
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Erfahren Sie, wie Sie Gruppen Lizenzen für die Verwendung mit Geräten zuweisen.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535662"
---
# <a name="manage-licenses-for-devices"></a>Verwalten von Lizenzen für Geräte

Wenn Sie über Microsoft 365 Apps for Enterprise (Gerät) oder Microsoft 365 Apps für Bildungseinrichtungen (Gerät) verfügen, können Sie Geräte Lizenzen mithilfe von Azure AD-Gruppen zuweisen. Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Microsoft 365 Apps for Enterprise (zuvor Office 365 ProPlus). Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden. Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Microsoft 365 Apps for Enterprise, ohne dass eine eigene Lizenz erforderlich ist.

> [!IMPORTANT]
> Die gerätebasierte Lizenzierung für Microsoft 365 Apps for Enterprise ist nur als Add-On-Lizenz für einige kommerzielle Kunden und einige Bildungskunden verfügbar. Für kommerzielle Kunden ist die Lizenz *Microsoft 365 Apps for Enterprise (Gerät)* und nur über Enterprise Agreement/Enterprise Agreement verfügbar. Für Bildungskunden ist die Lizenz Microsoft 365 Apps *Education (Device)* und nur über Enrollment for Education Solutions (EES) verfügbar. Weitere Informationen finden Sie im Blogbeitrag zur Verfügbarkeit [von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education). Wenden Sie sich zur kommerziellen Verfügbarkeit an Ihren Microsoft-Kontomitarbeiter.

Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen der Gruppe dann Geräte zu. Weitere Informationen zur Gerätelizenzierung, einschließlich gerätebasierter Anforderungen, zu den typen von Gruppen, die Sie verwenden können, und zum Konfigurieren von Microsoft 365 Apps for Enterprise für die Verwendung der Gerätelizenzierung finden Sie unter [Device-based licensing for Microsoft 365 Apps for Enterprise](/deployoffice/device-based-licensing).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.

## <a name="assign-licenses-to-devices"></a>Zuweisen von Lizenzen zu Geräten

Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu. Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.

1. Wechseln Sie Microsoft 365 Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a>
2. Wählen Sie **auf** der Seite Lizenzen **Microsoft 365 Apps Für Bildungseinrichtungen (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen aus.**
4. Beginnen Sie **im** Bereich Zuweisen von Lizenzen zu einem Gruppenbereich mit der Eingabe eines Gruppennamens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.
5. Wählen **Sie Zuweisen** aus, und wählen Sie dann Schließen **aus.**

## <a name="unassign-licenses-from-devices"></a>Zuweisen von Lizenzen von Geräten

Wenn Sie lizenzen aus einer Gruppe entfernen, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe. Alle Apps und ihre zugehörigen Daten sind dann schreibgeschützt.

1. Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a>
2. Wählen Sie **auf** der Seite Lizenzen **Microsoft 365 Apps Für Bildungseinrichtungen (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie die drei Punkte (weitere Aktionen) aus, und wählen Sie dann Lizenzen zuweisen **aus.**
4. Wählen Sie **im Dialogfeld Lizenzen** nicht zuweisen die Option **Unassign aus.**
