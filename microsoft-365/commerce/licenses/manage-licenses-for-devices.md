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
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331658"
---
# <a name="manage-licenses-for-devices"></a>Verwalten von Lizenzen für Geräte

Wenn Sie über Microsoft 365 Apps for Enterprise (Gerät) oder Microsoft 365 Apps for Education (Gerät) verfügen, können Sie Mithilfe von Azure AD-Gruppen Lizenzen zu Geräten zuweisen. Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Microsoft 365 Apps for Enterprise (zuvor Office 365 ProPlus genannt) verwenden. Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden. Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Microsoft 365 Apps for Enterprise, ohne dass eine eigene Lizenz erforderlich ist.

> [!IMPORTANT]
> Die gerätebasierte Lizenzierung für Microsoft 365 Apps for Enterprise ist nur als Add-On-Lizenz für einige kommerzielle Kunden und einige Bildungskunden verfügbar. Für kommerzielle Kunden ist die Lizenz *Microsoft 365 Apps for Enterprise (Gerät)* und nur über Konzernvertrag/Konzernvertrag verfügbar. Für Bildungskunden ist die Lizenz *Microsoft 365 Apps for Education (Gerät)* und nur über Enrollment for Education Solutions (EES) verfügbar. Weitere Informationen finden Sie im Blogbeitrag zur Verfügbarkeit [von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education). Wenden Sie sich zur kommerziellen Verfügbarkeit an Ihren Microsoft-Kontomitarbeiter.

Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen der Gruppe dann Geräte zu. Weitere Informationen zur Gerätelizenzierung, einschließlich gerätebasierter Anforderungen, der arten von Gruppen, die Sie verwenden können, und zum Konfigurieren von Microsoft 365 Apps for Enterprise für die Verwendung der Gerätelizenzierung finden Sie unter Gerätebasierte Lizenzierung für [Microsoft 365 Apps for Enterprise](/deployoffice/device-based-licensing).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.

## <a name="assign-licenses-to-devices"></a>Zuweisen von Lizenzen zu Geräten

Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu. Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a>
2. Wählen Sie **auf** der Seite Lizenzen **die Option Microsoft 365 Apps for Education (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen aus.**
4. Beginnen Sie **im** Bereich Zuweisen von Lizenzen zu einem Gruppenbereich mit der Eingabe eines Gruppennamens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.
5. Wählen **Sie Zuweisen** aus, und wählen Sie dann Schließen **aus.**

## <a name="unassign-licenses-from-devices"></a>Zuweisen von Lizenzen von Geräten

Wenn Sie lizenzen aus einer Gruppe entfernen, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe. Alle Apps und ihre zugehörigen Daten sind dann schreibgeschützt.

1. Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a>
2. Wählen Sie **auf** der Seite Lizenzen **die Option Microsoft 365 Apps for Education (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie **Weitere Aktionen** aus, und wählen Sie dann Lizenzen zuweisen **aus.**
4. Wählen Sie **im Dialogfeld Lizenzen** nicht zuweisen die Option **Unassign aus.**
