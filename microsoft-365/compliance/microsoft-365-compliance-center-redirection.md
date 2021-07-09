---
title: Umleiten von Benutzern aus dem Office 365 Security and Compliance Center zum Microsoft 365 Compliance Center
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Erfahren Sie mehr über das automatische Umleiten Office 365 Security and Compliance Center-Benutzer an die Microsoft 365 Compliance Center.
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339406"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Umleiten von Benutzern aus dem Office 365 Security and Compliance Center zum Microsoft 365 Compliance Center

In diesem Artikel wird erläutert, wie die automatische Umleitung für Benutzer funktioniert, die vom Office 365 Security and Compliance Center (protection.office.com) zum Microsoft 365 Compliance Center (compliance.microsoft.com) auf Compliancelösungen zugreifen.

## <a name="what-to-expect"></a>Das erwartet Sie

Die automatische Umleitung ist standardmäßig für alle Benutzer aktiviert, die auf die folgenden Compliance-bezogenen Lösungen in Office 365 Security and Compliance (protection.office.com) zugreifen:

- Verhinderung von Datenverlust (DLP)
- Klassifizierung
- Informationsgovernance
- Datensatzverwaltung
- Kommunikationscompliance (früher "Aufsicht")

Benutzer werden automatisch an die gleichen Compliancelösungen im Microsoft 365 Compliance Center (compliance.microsoft.com) weitergeleitet.

> [!NOTE]
> Bei anderen Compliancelösungen im Office 365 Security and Compliance Center verwalten Benutzer diese Lösungen weiterhin im Microsoft 365 Compliance Center oder im Office 365 Security and Compliance Center. Die automatische Umleitung für diese Compliancelösungen wird in Kürze verfügbar sein.

Dieses Feature und die zugehörigen Steuerelemente ermöglichen nicht die automatische Umleitung von Sicherheitsfeatures für Microsoft Defender für Office 365. Informationen zum Aktivieren der Umleitung für Sicherheitsfeatures finden Sie unter ["Umleiten von Konten von Microsoft Defender für Office 365 zum Microsoft 365 Security Center".](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kann ich zum früheren Portal zurückkehren?

Wenn etwas nicht für Sie funktioniert oder wenn Sie etwas nicht über das Microsoft 365 Compliance Center-Portal abschließen können, können Sie die automatische Umleitung für alle Benutzer vorübergehend deaktivieren.

> [!IMPORTANT]
> Die Microsoft 365 Compliance Center ist das Ersatzverwaltungsportal für Compliance-Lösungen, die derzeit im Office 365 Security and Compliance Center verwaltet werden. Alle Microsoft 365 Compliancelösungen werden ausschließlich im Microsoft 365 Compliance Center verwaltet. Das Deaktivieren der Umleitung zum Microsoft 365 Compliance Center sollte eine kurzfristige Lösung sein.

Führen Sie die folgenden Schritte aus, um zum Office 365 Security and Compliance Center (protection.microsoft.com) für alle Benutzer zurückzukehren:

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com) als globaler Administrator oder mit einem beliebigen Konto mit Complianceadministratorberechtigungen in Azure Active Directory an.
2. Navigieren Sie zu **Einstellungen**  >  **Compliance Center-Umleitung.**
3. Schalten Sie die Einstellung für die automatische Umleitung auf **"Aus" um.**
4. Wählen Sie **"Deaktivieren" und** "Feedback teilen" aus, wenn Sie dazu aufgefordert werden.

Nach der Deaktivierung werden die Benutzer nicht mehr an compliance.microsoft.com weitergeleitet und zum Office 365 Security and Compliance Center (protection.microsoft.com) weitergeleitet. Diese Einstellung kann von globalen oder Compliance-Administratoren jederzeit erneut aktiviert werden.

## <a name="related-information"></a>Verwandte Informationen

- [Übersicht über Microsoft 365 Compliance Center](/microsoft-365/compliance/microsoft-365-compliance-center)
