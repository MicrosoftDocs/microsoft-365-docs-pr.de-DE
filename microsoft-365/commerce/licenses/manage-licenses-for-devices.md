---
title: Verwalten von Lizenzen für Geräte
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826279"
---
# <a name="manage-licenses-for-devices"></a>Verwalten von Lizenzen für Geräte

Wenn Sie Office 365 ProPlus (Gerät) oder Office 365 ProPlus für Bildung (Gerät) haben, können Sie Geräte mithilfe von Azure AD Gruppenlizenzen zuweisen. Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Office 365 verwenden. Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden. Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Office 365, ohne dass eine eigene Lizenz erforderlich ist.

> [!IMPORTANT]
> Die gerätebasierte Lizenzierung für Office 365 ProPlus ist nur als Add-on-Lizenz für einige kommerzielle Kunden und einige Schulungs Kunden verfügbar. Für kommerzielle Kunden ist die Lizenz *Office 365 ProPlus (Gerät)* und steht nur über Enterprise Agreement/Enterprise Agreement Subscription zur Verfügung. Für Schulungs Kunden ist die Lizenz *Office 365 ProPlus für Bildung (Gerät)* und nur über die Registrierung für Education Solutions (EBS) verfügbar. Weitere Informationen finden Sie im Blogbeitrag zur [Verfügbarkeit von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Wenden Sie sich für kommerzielle Verfügbarkeit an Ihren Microsoft-Konto Vertreter.

Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen dann der Gruppe Geräte zu. Weitere Informationen zur Geräte Lizenzierung, einschließlich Geräteanforderungen, zu den Arten von Gruppen, die Sie verwenden können, und zum Konfigurieren von Office 365 ProPlus für die Verwendung der Geräte Lizenzierung finden Sie unter [gerätebasierte Lizenzierung für Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.

## <a name="assign-licenses-to-devices"></a>Zuweisen von Lizenzen zu Geräten

Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu. Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie **Licenses** auf der Seite Lizenzen **Office 365 ProPlus für Education (Gerät)** oder **Office ProPlus (Gerät)** aus.
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen**aus.
4. Geben Sie im Bereich **Lizenzen einer Gruppe zuweisen** die Eingabe eines Gruppennamens ein, und wählen Sie ihn aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.
5. Wählen Sie **assign**und dann **Close**aus.

## <a name="unassign-licenses-from-devices"></a>Aufheben der Zuweisung von Lizenzen von Geräten

Wenn Sie die Zuweisung von Lizenzen von einer Gruppe aufheben, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe. Alle apps und die zugehörigen Daten sind dann schreibgeschützt.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie **Licenses** auf der Seite Lizenzen **Office 365 ProPlus für Education (Gerät)** oder **Office ProPlus (Gerät)** aus.
3. Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie **Weitere Aktionen**aus, und wählen Sie dann Lizenzen für die **Zuweisung**aufheben aus.
4. Wählen Sie im Dialogfeld **Lizenzen** aufheben die Option **Zuweisung**aufheben aus.