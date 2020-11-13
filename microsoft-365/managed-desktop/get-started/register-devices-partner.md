---
title: Schritte für Partner zum Registrieren von Geräten
description: Wie Partner Geräte registrieren können, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071443"
---
# <a name="steps-for-partners-to-register-devices"></a>Schritte für Partner zum Registrieren von Geräten


In diesem Thema werden die Schritte beschrieben, die für Partner zum Registrieren von Geräten befolgt werden müssen. Das Verfahren zum Registrieren von Geräten selbst ist unter [Registrieren von Geräten in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.



## <a name="prepare-for-registration"></a>Vorbereiten der Registrierung 
Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit diesen im [Partner Center](https://partner.microsoft.com/dashboard)herstellen. Ausführliche Informationen zu diesem Prozess finden Sie in der [Zustimmungs Dokumentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) . Jeder CSP-Partner kann Geräte im Namen eines beliebigen Kunden hinzufügen, solange der Kunde dem zustimmt. Weitere Informationen zu Partnerbeziehungen und Autopilot-Berechtigungen finden Sie auch in der [Hilfe zum Partner Center](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Diese Dokumentation ist nur für Partner und OEMs. Der Prozess für die Selbstregistrierung ist in [Register Devices in Microsoft Managed Desktop selbst](register-devices-self.md)dokumentiert.


## <a name="register-devices-by-using-partner-center"></a>Registrieren von Geräten mithilfe des Partner Centers

Nachdem Sie die Beziehung mit ihren Kunden hergestellt haben, können Sie das Partner Center nutzen, um den Autopilot-Geräten für alle Kunden, mit denen Sie eine Beziehung haben, Geräte hinzuzufügen, indem Sie die folgenden Schritte ausführen:

1. Wechseln zum [Partner Center](https://partner.microsoft.com/dashboard)
2. Wählen Sie im Menü Partner Center die Option **Kunden** aus, und wählen Sie dann den Kunden aus, dessen Geräte Sie verwalten möchten.
3. Wählen Sie auf der Detailseite des Kunden **Geräte** aus.
4. Wählen Sie unter Profile auf Geräte **anwenden** die Option **Geräte hinzufügen** aus.
5. Geben Sie **Microsoft365Managed_Autopilot** für den Gruppennamen ein, und wählen Sie dann **Durchsuchen** aus, um die Liste des Kunden (im CSV-Dateiformat) in das Partner Center hochzuladen.


> [!IMPORTANT]
> Der Gruppen Name muss **Microsoft365Managed_Autopilot** genau übereinstimmen, einschließlich Groß-/Kleinschreibung und Sonderzeichen. Auf diese Weise können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.

>[!NOTE]
> Sie sollten diese CSV-Datei mit Ihrem Gerätekauf erhalten haben. Wenn Sie keine CSV-Datei erhalten haben, können Sie diese selbst erstellen, indem Sie die Schritte unter [Hinzufügen von Geräten zu Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)ausführen. Das Windows PowerShell Skript unterscheidet sich von dem, das für das [Verwaltungsportal von Microsoft Managed Desktop](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)verwendet wird. Partner sollten mithilfe von [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) Geräte für Microsoft Managed Desktop-Geräte im Partner Center registrieren.

Wenn Sie beim Hochladen der CSV-Datei eine Fehlermeldung erhalten, überprüfen Sie das Format der Datei. Stellen Sie sicher, dass die Spaltenreihenfolge den Anweisungen in [Verwenden von Windows Autopilot-Profilen auf neuen Geräten entspricht, um die Out-of-Box-Erfahrung eines Kunden anzupassen](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account). Sie können auch die CSV-Beispieldatei verwenden, die über den Link neben **Geräte hinzufügen** zum Erstellen einer Geräteliste bereitgestellt wird. 

Weitere Informationen zu Autopilot in Partner Szenarien finden Sie unter [Hinzufügen von Geräten zu einem Kundenkonto](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrieren von Geräten mithilfe der OEM-API

Bevor Sie die Registrierung für einen Kunden abschließen, müssen Sie zunächst eine Beziehung mit diesen herstellen. Sie sollten über einen eindeutigen Link verfügen, der ihren jeweiligen Kunden zur Verfügung steht. Weitere Informationen finden Sie unter [How to establish OEM Relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Nachdem Sie die Beziehung eingerichtet haben, können Sie mit der Gruppen-Tag- **Microsoft365Managed_Autopilot** die Registrierung von Geräten für Kunden beginnen.

> [!IMPORTANT]
> Der Gruppenname muss **Microsoft365Managed_Autopilot** genau übereinstimmen, einschließlich Groß-/Kleinschreibung und Sonderzeichen. Auf diese Weise können die neu registrierten Geräte dem Microsoft Managed Desktop Autopilot-Profil zugewiesen werden.
