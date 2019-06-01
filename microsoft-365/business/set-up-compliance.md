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
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Richten Sie Office 365 Advanced Threat Protection ein, und schützen Sie vertrauliche Daten.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668387"
---
# <a name="set-up-compliance-features"></a>Einrichten von Kompatibilitätsfeatures

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
    
4. Im Dialogfeld **Beweissicherungsverfahren** können Sie die Dauer des beweissicherungsverfahrens im Feld **Dauer des Beweis** Sicherungsverfahrens angeben, das Feld leer lassen, wenn Sie einen unbegrenzten Haltebereich platzieren möchten. Sie können auch Notizen hinzufügen und den Postfachbesitzer an eine Website weiterleiten, die möglicherweise mehr über das \> **** Beweissicherungsverfahren zu erklären ist.
    
**Aufbewahrung:** Sie können benutzerdefinierte Aufbewahrungsrichtlinien aktivieren, beispielsweise um eine bestimmte Zeitspanne beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="set-up-azure-information-protection-features"></a>Einrichten von Azure Information Protection-Features

Azure Information Protection (AIP) hilft Ihnen, Ihre Dokumente und e-Mails zu klassifizieren und optional zu schützen, indem Sie Bezeichnungen anwenden. Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen manuell von Benutzern definieren, oder indem Sie eine Kombination verwenden, in der Benutzern Empfehlungen gegeben werden.

In Outlook im Internet können Sie die folgenden integrierten Bezeichnungen und Einschränkungen auf Ihre e-Mails anwenden:
  
- **Nicht weiterleiten**: Empfänger können die Nachricht lesen, aber keine Inhalte weiterleiten, drucken oder kopieren
    
- **** Verschlüsseln: die gesamte Nachricht ist verschlüsselt. Empfänger müssen Ihre Identität vor dem Zugriff auf verschlüsselte Inhalte bestätigen und die Verschlüsselung nicht entfernen.
    
- **Vertraulich**: gibt den Mitarbeitern in Ihrer Organisation vollständige Berechtigungen für e-Mail-Inhalte und-Anlagen, jedoch nicht für Personen außerhalb Ihrer Organisation. Datenbesitzer können Inhalte an beliebiger Position nachverfolgen und widerrufen.
    
- **Streng vertraulich**: Diese Einschränkung kann auf streng vertrauliche Daten angewendet werden, sodass Mitarbeiter die Daten anzeigen, bearbeiten und beantworten, aber nicht weiterleiten, drucken oder kopieren können. Datenbesitzer können Inhalte an beliebiger Position nachverfolgen und widerrufen.

### <a name="make-sure-azure-information-protection-is-activated"></a>Stellen Sie sicher, dass Azure Information Protection aktiviert ist.

So stellen Sie sicher, dass AIP aktiviert ist:

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.

2. Wählen Sie **alle Dienste** aus, und geben Sie in das **Suchfeld** *Azure Information Protection* ein.

3. Nachdem die Ergebnisse angezeigt wurden, klicken Sie auf den Start neben **Azure Information Protection** , um ihn zu einem bevorzugten und leicht zu findenden späteren Zeitpunkt zu machen.

4. Wählen Sie **Azure Information Protection** \> **Protection-Aktivierung** aus, und stellen Sie sicher, dass der Status auf Aktiviert festgelegt ist. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Anzeigen der Azure Information Protection-Richtlinie und der Standardbeschriftungen 

So zeigen Sie die vorhandenen Bezeichnungen an und ändern Sie:

1. Wählen Sie im Azure Information Protection-Dashboard **Klassifikations** \> **Bezeichnungen**aus. <br/>![Standard Beschriftungen für Azure Information Protection.](media/AIPLabels.png)

2. Sie können eine beliebige Beschriftung auswählen, um Optionen anzuzeigen, Sie können den Anzeigenamen, die Farben usw. ändern.
 
3. Weitere Informationen finden Sie unter [ändern und Erstellen neuer Bezeichnungen](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) , wenn Sie eigene erstellen möchten. 

### <a name="install-the-azure-information-protection-client-manually"></a>Manuelles Installieren des Azure Information Protection-Clients

So installieren Sie den AIP-Client manuell:

1. Laden Sie **AzInfoProtection. exe** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter.
 
2. Sie können überprüfen, ob die Installation erfolgreich war, indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option **schützen** auf der Registerkarte **Start** zur Verfügung steht. <br/>![Dropdown-Registerkarte Schutz in einem Word-Dokument.](media/Word_Protect.png)

Weitere Informationen finden Sie unter [Installieren des Clients](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
