---
title: Ändern eines benutzerdefinierten vertraulichen Informationstyps mithilfe von PowerShell
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
description: Erfahren Sie, wie Sie benutzerdefinierte vertrauliche Informationen mithilfe von PowerShell ändern.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322696"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Ändern eines benutzerdefinierten vertraulichen Informationstyps mithilfe von PowerShell

Im Compliance Center PowerShell müssen Sie zum Ändern eines Typs für vertrauliche Informationen wie folgt vorgehen:

1. Exportieren Sie das vorhandene Regelpaket, das den benutzerdefinierten Typ für vertrauliche Informationen enthält, in eine XML-Datei (oder verwenden Sie die vorhandene XML-Datei, wenn Sie darüber verfügen).

2. Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.

3. Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.

Informationen zum Herstellen der Verbindung zu Compliance Center PowerShell finden Sie unter [Verbinden mit Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Schritt 1: Exportieren des vorhandenen Regelpakets in eine XML-Datei

> [!NOTE]
> Wenn Sie eine Kopie der XML-Datei haben (z. B. eine soeben erstellte und importierte Datei), können Sie mit dem nächsten Schritt fortfahren, in dem Sie die XML-Datei ändern.

1. Sollten Sie ihn noch nicht kennen, führen Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) aus, um den Namen des benutzerdefinierten Regelpakets zu ermitteln:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > Das integrierte Regelpaket, das die integrierten Typen vertraulicher Informationen enthält, heißt „Microsoft Regelpaket“. Das Regelpaket, das die benutzerdefinierten Typen vertraulicher Informationen enthält, die Sie in der Benutzeroberfläche von Compliance Center erstellt haben, heißt „Microsoft.SCCManaged.CustomRulePack“.

2. Verwenden Sie das Cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage), um das benutzerdefinierte Regelpaket in einer Variablen zu speichern:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Wenn der Name für das Regelpaket beispielsweise „Employee ID Custom Rule Pack“ lautet, führen Sie das folgende Cmdlet aus:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Verwenden Sie das Cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) zum Exportieren des benutzerdefinierten Regelpakets in eine XML-Datei:

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   In diesem Beispiel wird das Regelpaket in die Datei mit dem Namen „ExportedRulePackage.xml“ im Ordner „C:\Dokumente“ exportiert.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Schritt 2: Ändern Sie den benutzerdefinierten Typ für vertrauliche Informationen in der exportierten XML-Datei.

Typen für vertrauliche Informationen in der XML-Datei und andere Elemente in der Datei werden weiter oben in diesem Thema beschrieben.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Schritt 3: Importieren Sie die aktualisierte XML-Datei wieder in das vorhandene Regelpaket.

Verwenden Sie das Cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage), um die aktualisierte XML-Datei wieder in das vorhandene Regelpaket zu importieren:

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Ausführliche Informationen zur Syntax und zu den Parametern finden Sie unter [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).


## <a name="more-information"></a>Weitere Informationen

- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)

- [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md)
