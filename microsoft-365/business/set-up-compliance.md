---
title: Erhöhter Bedrohungsschutz für Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Einrichten von Compliance-Features, um Datenverlust zu verhindern und vertrauliche Daten zu kennzeichnen
ms.openlocfilehash: a0ba2fa6dbe7c786d577ad7098c1790f569f5acc
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453912"
---
# <a name="set-up-compliance-features"></a>Einrichten von Compliancefeatures

Ihr Microsoft 365 Business verfügt über Features zum Schutz Ihrer Daten und Geräte und hilft Ihnen dabei, die vertraulichen Informationen Ihrer Kunden sicher zu halten.

## <a name="set-up-dlp-features"></a>Einrichten von DLP-Features

Ein Beispiel zum Einrichten einer Richtlinie zum Schutz gegen personenbezogene Informationen (PII) finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP verfügt über viele vorgefertigte Richtlinienvorlagen für viele unterschiedliche Gebietsschemas. Zum Beispiel: Australien Financial Data, Canada Personal Information Act, US Financial Data, etc. Eine vollständige Liste finden Sie unter [was die DLP-Richtlinienvorlagen enthalten](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) . Alle diese Vorlagen können ähnlich wie beim PII-Vorlagenbeispiel aktiviert werden. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Einrichten der e-Mail-Aufbewahrung mit Exchange Online Archivierung

 **Exchange Online Archivierungs** Lizenz Funktionen unterstützen die Einhaltung von Vorschriften und behördlichen Vorgaben durch die Beibehaltung von e-Mail-Inhalten für eDiscovery. Es hilft auch, das Risiko im Fall eines Rechtsstreits zu verringern, und bietet eine Möglichkeit, Daten nach einer Sicherheitsverletzung wiederherzustellen, oder wenn Sie gelöschte Elemente wiederherstellen müssen. Sie können das Beweissicherungsverfahren verwenden, um alle Inhalte eines Benutzers beizubehalten, oder Sie verwenden Aufbewahrungsrichtlinien, um die beizubehaltenden Elemente anzupassen.
  
**Beweissicherungsverfahren:** Sie können alle Postfachinhalte einschließlich gelöschter Elemente beibehalten, indem Sie das gesamte Postfach eines Benutzers in das Beweissicherungsverfahren versetzen. 
    
So legen Sie ein Postfach für das Beweissicherungsverfahren im Admin Center ab:
    
1. Navigieren Sie im linken Navigationsbereich zu **Benutzer** \> **aktive Benutzer**.
    
2. Wählen Sie einen Benutzer aus, dessen Postfach Sie in das Beweissicherungsverfahren einfügen möchten, und klicken Sie im Benutzerbereich auf **e-Mail-Einstellungen** erweitern, und wählen Sie neben **Weitere Einstellungen** die Option **Exchange-Eigenschaften bearbeiten**aus.
    
3. Wählen Sie auf der Seite Postfachbenutzer im linken Navigationsbereich die Option * * Postfachfeatures * * aus, und wählen Sie dann den Link **aktivieren** unter **Beweissicherungsverfahren**aus.
    
4. Im Dialogfeld **Beweissicherungsverfahren** können Sie die Dauer des beweissicherungsverfahrens im Feld **Dauer des Beweis** Sicherungsverfahrens angeben, das Feld leer lassen, wenn Sie einen unbegrenzten Haltebereich platzieren möchten. Sie können auch Notizen hinzufügen und den Postfachbesitzer an eine Website weiterleiten, die möglicherweise mehr über das \> **Beweissicherungsverfahren**zu erklären ist.
    
**Aufbewahrung:** Sie können benutzerdefinierte Aufbewahrungsrichtlinien aktivieren, beispielsweise um eine bestimmte Zeitspanne beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-sensitivity-labels"></a>Einrichten von Sensitivitäts Bezeichnungen

Vertraulichkeits Bezeichnungen werden mit dem Azure Information Protection (AIP) Plan 1 geliefert und helfen Ihnen, Ihre Dokumente und e-Mails zu klassifizieren und optional zu schützen, indem Sie Bezeichnungen anwenden. Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen manuell von Benutzern definieren, oder indem Sie eine Kombination verwenden, in der Benutzern Empfehlungen gegeben werden.

Um Sensitivitäts Bezeichnungen einzurichten, zeigen Sie Video zu [Erstellen und Verwalten von Sensitivitäts Bezeichnungen](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) an.



### <a name="install-the-azure-information-protection-client-manually"></a>Manuelles Installieren des Azure Information Protection-Clients

So installieren Sie den AIP-Client manuell:

1. Laden Sie **AzinfoProtection_UL. exe** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter.
 
2. Sie können überprüfen, ob die Installation erfolgreich war, indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option **Vertraulichkeit** auf der Registerkarte **Start** verfügbar ist.
<br/>![Dropdown-Registerkarte Schutz in einem Word-Dokument.](media/word-sensitivity.png)

Weitere Informationen finden Sie unter [Installieren des Clients](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
