---
title: Entfernen eines benutzerdefinierten vertraulichen Informationstyps mithilfe von PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie einen benutzerdefinierten vertraulichen Informationstyp mithilfe von PowerShell entfernen
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322693"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Entfernen eines benutzerdefinierten vertraulichen Informationstyps mithilfe von PowerShell



Im Compliance Center PowerShell gibt es zwei Methoden zum Entfernen eines benutzerdefinierten Typs für vertrauliche Informationen:

- **Entfernen einzelner benutzerdefinierter Typen vertraulicher Informationen:** Verwenden Sie die in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)dokumentierte Methode. Sie exportieren das benutzerdefinierte Regelpaket, das den benutzerdefinierten Typ vertraulicher Informationen enthält, entfernen den Vertraulichen Informationstyp aus der XML-Datei, und importieren die aktualisierte XML-Datei wieder in das vorhandene benutzerdefinierte Regelpaket.

- **Entfernen eines benutzerdefinierten Regelpakets und aller benutzerdefinierten Typen für vertrauliche Informationen, die darin enthalten sind**: Diese Methode ist in diesem Abschnitt aufgeführt.

> [!NOTE]
> Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.

1. [Verbindung mit Compliance Center-PowerShell herstellen](/powershell/exchange/exchange-online-powershell)

2. Wenn Sie ein benutzerdefiniertes Regelpaket entfernen möchten, verwenden Sie das Cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Sie können den Wert „Name“ (für jede Sprache) oder den Wert `RulePack id` (GUID) verwenden, um das Regelpaket zu identifizieren.

   In diesem Beispiel wird das Regelpaket mit dem Namen „Employee ID Custom Rule Pack“ entfernt.

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Ausführliche Informationen zur Syntax und den Parametern finden Sie unter [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).

3. Um sicherzustellen, dass Sie einen benutzerdefinierten Typen für vertrauliche Informationen erfolgreich entfernt haben, führen Sie einen der folgenden Schritte aus:

   - Führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) aus und vergewissern Sie sich, dass das Regelpaket nicht mehr aufgeführt wird:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Führen Sie das Cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) aus und stellen Sie sicher, dass die Typen für vertrauliche Informationen im entfernten Regelpaket nicht mehr aufgeführt werden:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Bei benutzerdefinierten Typen für vertrauliche Informationen ist der Publisher-Eigenschaftswert ein anderer als „Microsoft Corporation“.

   - Ersetzen Sie \<Name\> durch den Namenswert des Typs für vertrauliche Informationen (z. B. die Mitarbeiter-ID), und führen Sie das Cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) aus, um sicherzustellen, dass der Typ für vertrauliche Informationen nicht mehr aufgeführt wird:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Weitere Informationen

- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)

- [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md)
