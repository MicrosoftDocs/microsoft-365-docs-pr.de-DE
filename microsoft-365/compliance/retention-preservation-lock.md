---
title: Verwenden der Erhaltungssperre zum Einschränken von Änderungen an Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Verwenden Sie die Erhaltungssperre mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien, um die Einhaltung behördlicher Vorschriften und die Absicherung gegen übel gesinnte Administratoren zu erleichtern.
ms.openlocfilehash: 9890c73495bd14ea7264f3314f6313254ef1bf6b
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612987"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Verwenden der Erhaltungssperre zum Einschränken von Änderungen an Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Erhaltungssperre sperrt eine Aufbewahrungsrichtlinie oder eine Aufbewahrungsbezeichnungsrichtlinie, sodass niemand – auch nicht ein globaler Administrator – die Richtlinie deaktivieren, löschen oder weniger restriktiv einstellen kann. Diese Konfiguration könnte aufgrund behördlicher Vorschriften erforderlich sein und kann zum Schutz vor übel gesinnten Administratoren beitragen.

Das Sperren einer Aufbewahrungsrichtlinie bewirkt Folgendes:

- Niemand kann die Richtlinie deaktivieren oder löschen.
- Speicherorte können hinzugefügt, aber nicht entfernt werden.
- Der Aufbewahrungszeitraum kann verlängert, jedoch nicht verringert werden.

Das Sperren einer Aufbewahrungsbezeichnungsrichtlinie bewirkt Folgendes:

- Niemand kann die Richtlinie deaktivieren oder löschen.
- Speicherorte können hinzugefügt, aber nicht entfernt werden.
- Bezeichnungen können hinzugefügt, aber nicht entfernt werden.

Zusammenfassend kann man sagen, dass eine gesperrte Richtlinie erweitert oder verlängert, jedoch nicht reduziert oder deaktiviert werden kann.

> [!IMPORTANT]
> Bevor Sie eine Aufbewahrungsrichtlinie oder einen Aufbewahrungsbezeichnungsrichtlinie sperren, ist es wichtig, dass Sie die Auswirkungen kennen und überlegen, ob dies für Ihre Organisation erforderlich ist. Es könnte beispielsweise zur Erfüllung behördlicher Vorschriften erforderlich sein. Administratoren können diese Richtlinien nicht mehr deaktivieren oder löschen, nachdem die Erhaltungssperre auf sie angewendet wurde.

Konfigurieren Sie die Erhaltungssperre, nachdem Sie eine [Aufbewahrungsrichtlinie](create-retention-policies.md) oder eine Aufbewahrungsbezeichnungsrichtlinie erstellt haben, die Sie [veröffentlichen](create-apply-retention-labels.md) oder die [automatisch angewendet wird](apply-retention-labels-automatically.md). 

> [!NOTE]
> Das Sperren einer Bezeichnungsrichtlinie hindert einen Administrator nicht daran, die Aufbewahrungszeit für eine Bezeichnung, die in der gesperrten Richtlinie enthalten ist, zu verkürzen. Diese Anforderung kann, zusammen mit anderen Einschränkungen, erfüllt werden, wenn Sie eine Bezeichnung konfigurieren, um Elemente als [Datensatz](records-management.md#records) zu markieren.

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>So sperren Sie eine Aufbewahrungsrichtlinie oder Aufbewahrungsbezeichnungsrichtlinie

Sie müssen PowerShell verwenden, wenn eine Erhaltungssperre angewendet werden soll. Da Administratoren nach dem Anwenden dieser Sperre eine Richtlinie für die Aufbewahrung nicht mehr deaktivieren oder löschen können, kann dieses Feature nicht über die Benutzeroberfläche aktiviert werden, um eine unbeabsichtigte Konfiguration zu verhindern.

Alle Richtlinien für die Aufbewahrung und mit beliebiger Konfiguration unterstützen die Aufbewahrungssperre.

1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Führen Sie zum Suchen nach dem Namen der Richtlinie, die Sie sperren möchten, den Befehl [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy) aus. Zum Beispiel:
    
   ![Liste der Aufbewahrungsrichtlinien in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Um eine Aufbewahrungssperre auf Ihre Aufbewahrungsrichtlinie anzuwenden, führen Sie das Cmdlet [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) mit dem Namen der Richtlinie aus, und legen Sie den Parameter *RestrictiveRetention* auf „true“ fest:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Zum Beispiel:
    
    ![RestrictiveRetention-Parameter in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Wenn Sie dazu aufgefordert werden, lesen und bestätigen Sie die Einschränkungen, die in dieser Konfiguration enthalten sind, indem Sie **J** eingeben:
    
   ![Aufforderung zur Bestätigung der Sperre einer Aufbewahrungsrichtlinie in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Eine Aufbewahrungssperre wird jetzt auf die Richtlinie angewendet. Führen Sie `Get-RetentionCompliancePolicy` zur Bestätigung erneut aus, geben Sie aber den Namen der Richtlinie an, und zeigen Sie die Richtlinienparameter an:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Sie sollten sehen, dass **RestrictiveRetention** auf **True** festgelegt wurde. Zum Beispiel:

![Gesperrte Richtlinie mit allen Parametern in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>Weitere Informationen

[Ressourcen, die Sie bei der Einhaltung behördlicher Vorschriften für Informationsgovernance und Datensatzverwaltung unterstützen](retention-regulatory-requirements.md)
