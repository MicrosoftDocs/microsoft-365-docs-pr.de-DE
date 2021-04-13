---
title: Schritte für Partner zum Registrieren von Geräten
description: So können Partner Geräte registrieren, damit sie von Microsoft Managed Desktop verwaltet werden können
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689233"
---
# <a name="steps-for-partners-to-register-devices"></a>Schritte für Partner zum Registrieren von Geräten


In diesem Artikel werden die Schritte beschrieben, die Partner befolgen müssen, um Geräte zu registrieren. Der Prozess zum Registrieren von Geräten selbst ist unter Registrieren von Geräten [in Microsoft Managed Desktop selbst dokumentiert.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Vorbereiten der Registrierung 
Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit ihnen im [Partner Center einrichten.](https://partner.microsoft.com/dashboard) Weitere Informationen [zu diesem Prozess finden](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) Sie in der Zustimmungsdokumentation. Jeder #A0 kann Geräte im Namen eines beliebigen Kunden hinzufügen, solange der Kunde zuwilligt. Weitere Informationen zu Partnerbeziehungen und Autopilotberechtigungen finden Sie in der [Partner Center-Hilfe.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Diese Dokumentation ist nur für Partner und OEMs. Der Prozess für die Selbstregistrierung ist unter Registrieren von Geräten [in Microsoft Managed Desktop selbst dokumentiert.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrieren von Geräten mithilfe von Partner Center

Nachdem Sie die Beziehung zu Ihren Kunden eingerichtet haben, können Sie das Partner Center verwenden, um Autopilot Geräte für jeden Kunden hinzuzufügen, mit dem Sie eine Beziehung haben, indem Sie die folgenden Schritte ausführen:

1. Navigieren zu [Partner Center](https://partner.microsoft.com/dashboard)
2. Wählen **Sie im** Menü Partner Center die Option Kunden aus, und wählen Sie dann den Kunden aus, dessen Geräte Sie verwalten möchten.
3. Wählen Sie auf der Detailseite des Kunden Geräte **aus.**
4. Wählen **Sie unter Profile auf** Geräte anwenden die Option Geräte hinzufügen **aus.**
5. Geben Sie das entsprechende Gruppentag für das ausgewählte Geräteprofil ein (wie in der folgenden Tabelle dargestellt), und wählen Sie dann **Durchsuchen** aus, um die Kundenliste (im CSV-Dateiformat) in das Partner Center hochzuladen.

|[Geräteprofil](../service-description/profiles.md)  |Gruppentag  |
|---------|---------|
|Vertrauliche Daten     |**Microsoft365Managed \_ SensitiveData**    |
|Power User     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> Der Gruppenname muss genau mit den in der Tabelle aufgeführten übereinstimmen, einschließlich Groß- und Sonderzeichen. Dadurch können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.

>[!NOTE]
> Sie sollten diese CSV-Datei mit dem Gerätekauf erhalten haben. Wenn Sie keine CSV-Datei erhalten haben, können Sie diese selbst erstellen, indem Sie die Schritte unter Hinzufügen von Geräten [zu Windows Autopilot ausführen.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Das Windows PowerShell-Skript ist anders als das für das [Microsoft Managed Desktop Admin-Portal .](./register-devices-self.md#obtain-the-hardware-hash) Partner sollten [Get-WindowsAutoPilotInfo verwenden,](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) um Geräte für Microsoft Managed Desktop-Geräte im Partner Center zu registrieren.

Wenn beim Hochladen der CSV-Datei eine Fehlermeldung angezeigt wird, überprüfen Sie das Format der Datei. Stellen Sie sicher, dass die Spaltenreihenfolge mit den unter Verwenden von Windows Autopilot-Profilen auf neuen Geräten beschriebenen Informationen zum Anpassen der [out-of-box-Benutzererfahrung](/partner-center/autopilot#add-devices-to-a-customers-account)eines Kunden entspricht. Sie können auch die CSV-Beispieldatei verwenden, die über den Link neben Geräte hinzufügen bereitgestellt wird, **um** eine Geräteliste zu erstellen. 

Weitere Informationen zu Autopilot in Partnerszenarien finden Sie unter Hinzufügen von Geräten [zum Kundenkonto](/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrieren von Geräten mithilfe der OEM-API

Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit ihnen einrichten. Sie sollten über einen eindeutigen Link verfügen, der Ihren jeweiligen Kunden zur Verfügung stellt. Weitere [Informationen finden Sie unter Einrichten einer OEM-Beziehung.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Nachdem Sie die Beziehung eingerichtet haben, können Sie mit der Registrierung von Geräten für Kunden beginnen, indem Sie das entsprechende Gruppentag für jedes ausgewählte Geräteprofil verwenden:


|Geräteprofil  |Gruppentag  |
|---------|---------|
|Vertrauliche Daten     | **Microsoft365Managed \_ SensitiveData**     |
|Power User     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> Die Gruppentags müssen genau mit den in der Tabelle aufgeführten übereinstimmen, einschließlich Groß- und Sonderzeichen. Dadurch können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.