---
title: Entfernen von Geräten
description: Entfernen von Geräten aus Microsoft Managed Desktop Verwaltung
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893815"
---
# <a name="remove-devices"></a>Entfernen von Geräten

Sie können Geräte aus Microsoft Managed Desktop Verwaltung entfernen, indem Sie das Administratorportal verwenden. Diese Aktion ist dauerhaft, Sie können sie jedoch erneut Microsoft Managed Desktop registrieren, indem Sie die [Registrierungsschritte ausführen.](../get-started/register-devices-self.md)

Wenn Sie ein Gerät entfernen, treten alle folgenden Schritte auf:

- Wir entfernen das Gerät aus Autopilot.
- Wir entfernen das Gerät aus allen "Modern Workplace"-Gerätegruppen.
- Wir entfernen das Gerät aus dem **Blatt Geräte** im Administratorportal.

Wenn Sie ein Gerät entfernen, haben Sie die Möglichkeit, es auch aus Azure Active Directory (Azure AD) und Microsoft Intune.
 
> [!CAUTION]
> Das Entfernen der Objekte im Zusammenhang mit einem Gerät aus Azure AD und Microsoft Intune ist dauerhaft. Wenn Sie die Objekte entfernen, können Sie die Geräte nicht in den Intune- und Azure-Portalen anzeigen oder verwalten. Die Geräte können nicht auf die Unternehmensressourcen ihres Unternehmens zugreifen. Unternehmensdaten werden möglicherweise aus ihnen gelöscht, wenn die Geräte versuchen, sich nach dem Löschen zu registrieren.

1. Wählen [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)im linken **Navigationsbereich** Geräte aus.
2. Suchen Sie nach **Microsoft Managed Desktop** im Menü, und wählen Sie **Geräte aus.**
3. Wählen Sie im Microsoft Managed Desktop Arbeitsbereich Geräte die Geräte aus, die Sie löschen möchten.
4. Wählen **Sie Geräteaktionen** aus, und wählen Sie dann **Gerät löschen aus,** das ein Fly-In öffnet, um die Geräte zu entfernen.
5. Überprüfen Sie im Fly-In die ausgewählten Geräte, und wählen Sie **dann Geräte entfernen aus.** Wenn Sie gleichzeitig auch die Azure AD- und Intune-Objekte entfernen möchten, aktivieren Sie das Kontrollkästchen. Die Geräteentfernung kann einige Minuten dauern.

> [!NOTE]
> Geräte, die sich in einem ausstehenden Registrierungsstatus befinden, können **nicht** entfernt werden.