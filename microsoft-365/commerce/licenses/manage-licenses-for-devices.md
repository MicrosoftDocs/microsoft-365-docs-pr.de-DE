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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242325"
---
# <a name="manage-licenses-for-devices"></a>Verwalten von Lizenzen für Geräte

Wenn Sie Office 365 ProPlus für Bildung (Gerät) haben, können Sie Geräte mithilfe von Azure AD Gruppenlizenzen zuweisen. Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Office 365 verwenden. Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden. Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Office 365, ohne dass eine eigene Lizenz erforderlich ist.

> [!IMPORTANT]
> Office 365 ProPlus für Education (Gerät) steht nur für Education a3-und A5-Volumenlizenzkunden zur Verfügung.

Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen dann der Gruppe Geräte zu. Weitere Informationen zur Geräte Lizenzierung, einschließlich Geräteanforderungen, zu den Arten von Gruppen, die Sie verwenden können, und zum Konfigurieren Office 365 ProPlus für die Verwendung der Geräte Lizenzierung finden Sie unter [Geräte Lizenzierung für Office 365 ProPlus für Education-Kunden](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.

## <a name="assign-licenses-to-devices"></a>Zuweisen von Lizenzen zu Geräten

Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu. Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie **** auf der Seite Lizenzen **Office 365 ProPlus für Bildung (Gerät)** aus.
3. Wählen Sie auf der Seite **Office 365 ProPlus-Education (Gerät)** ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen**aus.
4. Geben Sie im Bereich **Lizenzen einer Gruppe zuweisen** die Eingabe eines Gruppennamens ein, und wählen Sie ihn aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.
6. Wählen Sie **assign**und dann **Close**aus.

## <a name="unassign-licenses-from-devices"></a>Aufheben der Zuweisung von Lizenzen von Geräten

Wenn Sie die Zuweisung von Lizenzen von einer Gruppe aufheben, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe. Alle apps und die zugehörigen Daten sind dann schreibgeschützt.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie **** auf der Seite Lizenzen **Office 365 ProPlus für Bildung (Gerät)** aus.
3. Wählen Sie auf der Seite **Office 365 ProPlus-Education (Gerät)** ein Abonnement aus, wählen Sie **Weitere Aktionen**aus, und wählen Sie dann Lizenzen für die **Zuweisung**aufheben aus.
5. Wählen Sie im Dialogfeld **Lizenzen** aufheben die Option **Zuweisung**aufheben aus.