---
title: Erhöhen des Bedrohungsschutzes für Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Richten Sie Compliancefeatures ein, um Datenverluste zu verhindern und die vertraulichen Informationen Ihrer und Ihrer Kunden zu schützen.
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579952"
---
# <a name="set-up-compliance-features"></a>Einrichten von Compliancefeatures

Ihr Microsoft 365 Business Premium verfügt über Features zum Schutz Ihrer Daten und Geräte und hilft Ihnen, die vertraulichen Informationen Ihrer Kunden und Ihrer Kunden zu schützen.

## <a name="set-up-dlp-features"></a>Einrichten von DLP-Features

Ein Beispiel zum Einrichten einer Richtlinie zum Schutz vor Verlust personenbezogener Daten finden Sie unter Erstellen einer [DLP-Richtlinie](../compliance/create-a-dlp-policy-from-a-template.md) aus einer Vorlage. 
  
DLP enthält viele einsatzbereite Richtlinienvorlagen für viele verschiedene Locales. Beispiel: Australische Finanzdaten, Canada Personal Information Act, U.S. Financial Data und so weiter. Eine vollständige Liste finden Sie unter Was [die DLP-Richtlinienvorlagen](../compliance/what-the-dlp-policy-templates-include.md) enthalten. Alle diese Vorlagen können ähnlich wie im Beispiel für piI-Vorlagen aktiviert werden. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Einrichten der E-Mail-Aufbewahrung mit Exchange Online-Archivierung

 **Exchange Online-Archivierung** Lizenzfeatures helfen bei der Aufrechterhaltung von Compliance- und behördlichen Standards, indem E-Mail-Inhalte für eDiscovery beibehalten werden. Es hilft auch, Ihr Risiko zu reduzieren, wenn eine Klage vorlag, und bietet eine Möglichkeit, Daten nach einer Sicherheitsverletzung oder wenn Sie gelöschte Elemente wiederherstellen müssen. Sie können das Verfahrensverfahren verwenden, um alle Inhalte eines Benutzers zu erhalten, oder Aufbewahrungsrichtlinien verwenden, um die Aufbewahrungsrichtlinien anzupassen.
  
**Halterecht für Rechtsstreitigkeiten:** Sie können alle Postfachinhalte, einschließlich gelöschter Elemente, beibehalten, indem Sie das gesamte Postfach eines Benutzers in einem Rechtsstreit zurückhalten. 
    
So platzieren Sie ein Postfach in einem Rechtsstreit im Admin Center:
    
1. Wechseln Sie im linken Navigations navi zu **Benutzer** \> **Aktive Benutzer**.
    
2. Wählen Sie einen Benutzer aus, dessen Postfach Sie in einem Prozesssicherungsverfahren platzieren möchten. Erweitern Sie im Benutzerbereich **E-Mail-Einstellungen,** und wählen Sie neben **Weitere Einstellungen** die Option **Exchange-Eigenschaften bearbeiten aus.**
    
3. Wählen Sie auf der Postfachseite für den Benutzer ** Postfachfunktionen ** im linken Navigationsgerät aus, und wählen Sie dann den Link Aktivieren **unter** **Rechtsstreitigkeiten aus.**
    
4. Im Dialogfeld **Prozesssicherungsverfahren** können Sie die Dauer des Prozesssicherungsverfahren im Feld Dauer des **Rechtsstreitigkeiten-Haltebereichs** angeben. Lassen Sie das Feld leer, wenn Sie einen unendlichen Haltebereich platzieren möchten. Sie können auch Notizen hinzufügen und den Postfachbesitzer zu einer Website führen, auf der Sie möglicherweise weitere Informationen zum Prozesssicherungsverfahren erläutern müssen. \>**Speichern** Sie .
    
**Aufbewahrung:** Sie können beispielsweise angepasste Aufbewahrungsrichtlinien aktivieren, um inhalte für einen bestimmten Zeitraum zu erhalten oder Inhalte am Ende des Aufbewahrungszeitraums dauerhaft zu löschen. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](../compliance/retention.md).

## <a name="set-up-sensitivity-labels"></a>Einrichten von Vertraulichkeitsbezeichnungen

Vertraulichkeitsbezeichnungen sind in Azure Information Protection (AIP) Plan 1 enthalten und helfen Ihnen, Ihre Dokumente und E-Mails durch Anwenden von Bezeichnungen zu klassifizieren und optional zu schützen. Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen definieren, manuell von Benutzern oder mithilfe einer Kombination, in der Benutzern Empfehlungen gegeben werden.

Zum Einrichten von Vertraulichkeitsbezeichnungen zeigen Sie video [zum Erstellen und Verwalten von Vertraulichkeitsbezeichnungen](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) an.



### <a name="install-the-azure-information-protection-client-manually"></a>Manuelles Installieren des Azure Information Protection-Clients

So installieren Sie den AIP-Client manuell:

1. Laden **AzinfoProtection_UL.exe** von [Microsoft Download Center herunter.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. Sie können überprüfen, ob die Installation funktioniert hat,  indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option Vertraulichkeit auf der Registerkarte **Start verfügbar** ist.
<br/>![Dropdownliste "Registerkarte Schutz" in einem Word-Dokument.](../media/word-sensitivity.png)

Weitere Informationen finden Sie unter [Install the client](/azure/information-protection/infoprotect-tutorial-step3).