---
title: Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratoren können erfahren, wie Sie das Administrator-Überwachungsprotokoll in eigenständigem Exchange Online Protection (EOP) anzeigen und durchsuchen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286477"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung

**Gilt für**
- [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie das Exchange Admin Center (EAC) oder die eigenständige EOP PowerShell verwenden, um Einträge im Administrator-Überwachungsprotokoll zu suchen und diese ein- und auszusuchen.

Im Administrator-Überwachungsprotokoll werden bestimmte Aktionen aufgezeichnet, die auf eigenständigen EOP -PowerShell-Cmdlets basieren, die von Administratoren und Benutzern durchgeführt werden, denen Administratorrechte zugewiesen wurden. Einträge im Administrator-Überwachungsprotokoll enthalten Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.

> [!NOTE]
>
> - Die Administratorüberwachungsprotokollierung ist standardmäßig aktiviert und kann nicht deaktiviert werden.
>
> - Im Administrator-Überwachungsprotokoll werden keine Aktionen aufgezeichnet, die auf Cmdlets basieren, die mit den Verben **Get,** **Search** oder **Test beginnen.**
>
> - Die Überwachungsprotokolleinträge werden 90 Tage lang aufbewahrt. Wenn ein Eintrag älter als 90 Tage ist, wird er gelöscht.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die  Rolle **"Überwachungsprotokolle"** oder "Überwachungsprotokolle nur anzeigen", die standardmäßig den Rollengruppen "Organisationsverwaltung", "Complianceverwaltung" und "Sicherheitsadministrator" zugewiesen sind.    Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)-Forum um Hilfe.

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Anzeigen des Administrator-Überwachungsprotokolls mithilfe der EAC

1. Wechseln Sie in der EAC zu **Überwachung** der Verwaltung der Richtlinienverwaltung, und wählen Sie dann \>  **"Administratorüberwachungsprotokollbericht ausführen" aus.**

2. Wählen Sie **auf** der Seite "Nach Änderungen an Administrator-Rollengruppen suchen", die geöffnet wird, ein **Startdatum** und ein **Enddatum** aus (der Standardbereich ist die letzten zwei Wochen), und wählen Sie dann **Suche aus.** Sämtliche Konfigurationsänderungen, die im angegebenen Zeitraum erfolgt sind, werden angezeigt und können anhand der folgenden Informationen sortiert werden:

   - **Datum**: Datum und Uhrzeit der Konfigurationsänderung. Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.

   - **Cmdlet:** Der Name des Cmdlets, das zum Ändern der Konfiguration verwendet wurde.

   - **Benutzer:** Der Name des Benutzerkontos des Benutzers, der die Konfigurationsänderung vorgenommen hat.

     Es können bis zu 5000 Einträge auf mehreren Seiten angezeigt werden. Geben Sie einen kürzeren Datumsbereich ein, wenn Sie Ihre Ergebnisse eingrenzen möchten. Wenn Sie ein einzelnes Suchergebnis auswählen, werden im Detailbereich die folgenden weiteren Informationen angezeigt:

   - **Objekt geändert:** Das Objekt, das vom Cmdlet geändert wurde.

   - **Parameter (Parameter:Wert):** Die verwendeten Cmdlet-Parameter und alle mit dem Parameter angegebenen Werte.

3. Wenn Sie einen bestimmten Überwachungsprotokolleintrag drucken möchten, klicken Sie im Detailbereich auf die Schaltfläche **Drucken**.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Verwenden der eigenständigen EOP PowerShell zum Anzeigen des Administrator-Überwachungsprotokolls

Sie können die eigenständige EOP PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die den von Ihnen angegebenen Kriterien entsprechen. Verwenden Sie die folgende Syntax:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Hinweise**:

- Sie können den Parameter _"Parameters"_ nur zusammen mit dem _Parameter "Cmdlets"_ verwenden.

- Der _Parameter "ObjectIds"_ filtert die Ergebnisse nach dem Objekt, das vom Cmdlet geändert wurde. Ein gültiger Wert hängt davon ab, wie das Objekt im Überwachungsprotokoll dargestellt wird. Zum Beispiel:

  - Name
  - Kanonischer Distinguished Name (z. B. contoso.com/Users/Akia Al-Zuhairi)

  Wahrscheinlich müssen Sie andere Filterparameter für dieses Cmdlet verwenden, um die Ergebnisse einengt und die Objekttypen zu identifizieren, die Sie interessieren.

- Der _Parameter "UserIds"_ filtert die Ergebnisse nach dem Benutzer, der die Änderung vorgenommen hat (der das Cmdlet verwendet hat).

- Wenn Sie _für die Parameter "StartDate"_ und _"EndDate"_ einen Datums-/Uhrzeitwert ohne Zeitzone angeben, wird der Wert in koordinierter Weltzeit (Coordinated Universal Time, UTC) angegeben. Verwenden Sie eine der folgenden Optionen, um einen Datum/Uhrzeit-Wert für diesen Parameter anzugeben:

  - Datum/Uhrzeit-Wert in UTC, z. B.: "2016-05-06 14:30:00z".

  - Geben Sie den Wert für Datum/Uhrzeit als Formel an, die Datum/Uhrzeit in Ihrer lokalen Zeitzone in UTC konvertiert: z. B. `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Weitere Informationen finden Sie unter [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).

- Das Cmdlet gibt standardmäßig maximal 1.000 Protokolleinträge zurück. Verwenden Sie _den Parameter "ResultSize",_ um bis zu 250.000 Protokolleinträge anzugeben. Oder verwenden Sie den `Unlimited` Wert, um alle Einträge zurückzukehren.

In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:

- **Startdatum:** 4. August 2019
- **Enddatum:** 3. Oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Anzeigen der Details von Überwachungsprotokolleinträgen

Das **Cmdlet Search-AdminAuditLog** gibt die Felder zurück, die weiter unten in diesem Artikel im Abschnitt ["Überwachungsprotokollinhalte"](#audit-log-contents) beschrieben werden. Von den vom Cmdlet zurückgegebenen Feldern enthalten die beiden Felder **CmdletParameters** und **ModifiedProperties** zusätzliche Informationen, die standardmäßig nicht zurückgegeben werden.

Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.

1. Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen `$Results` gespeichert. Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an. Arrayelementindizes beginnen für das erste Arrayelement bei 0. Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.

    ```PowerShell
    $Results[4]
    ```

3. Der oben stehende Befehl gibt den im Arrayelement 4 gespeicherten Protokolleintrag zurück. Zum Anzeigen der Felder **CmdletParameters** und **ModifiedProperties** für diesen Protokolleintrag verwenden Sie die folgenden Befehle.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Um die Inhalte der Felder **CmdletParameters** und **ModifiedParameters** in einem anderen Protokolleintrag anzuzeigen, ändern Sie den Arrayelementindex.

## <a name="audit-log-contents"></a>Inhalte des Überwachungsprotokolls

Jeder Überwachungsprotokolleintrag enthält die Informationen, die in der folgenden Tabelle beschrieben sind. Das Überwachungsprotokoll enthält mindestens einen Überwachungsprotokolleintrag.

****

|Feld|Beschreibung|
|---|---|
|`RunspaceId`|Dieses Feld wird intern von EOP verwendet.|
|`ObjectModified`|Dieses Feld enthält das Objekt, das durch das im Feld angegebene Cmdlet geändert `CmdletName` wurde.|
|`CmdletName`|Dieses Feld enthält den Namen des Cmdlets, das vom Benutzer im Feld ausgeführt `Caller` wurde.|
|`CmdletParameters`|Dieses Feld enthält die Parameter, die angegeben wurden, als das Cmdlet im `CmdletName` Feld ausgeführt wurde. In diesem Feld wird auch, falls vorhanden, der in diesem Parameter angegebene Wert gespeichert, er wird jedoch nicht in der Standardausgabe angezeigt.|
|`ModifiedProperties`|Dieses Feld enthält die Eigenschaften, die für das Objekt im Feld geändert `ObjectModified` wurden. In diesem Feld werden auch der alte Wert der Eigenschaft und der neue gespeicherte Wert gespeichert, sie werden jedoch nicht in der Standardausgabe angezeigt.|
|`Caller`|Dieses Feld enthält das Benutzerkonto des Benutzers, der das Cmdlet im Feld verwendet `CmdletName` hat.|
|`ExternalAccess`|Dieses Feld wird intern von EOP verwendet.|
|`Succeeded`|Dieses Feld gibt an, ob das Cmdlet im `CmdletName` Feld erfolgreich abgeschlossen wurde. Der Wert ist entweder `True` oder `False` .|
|`Error`|Dieses Feld enthält die Fehlermeldung, die generiert wird, wenn das Cmdlet im Feld `CmdletName` nicht erfolgreich abgeschlossen werden konnte.|
|`RunDate`|Dieses Feld enthält Datum und Uhrzeit der Ausführung des Cmdlets im `CmdletName` Feld. Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.|
|`OriginatingServer`|Dieses Feld gibt den Server an, auf dem das im Feld angegebene Cmdlet `CmdletName` ausgeführt wurde.|
|`ClientIP`|Dieses Feld wird intern von EOP verwendet.|
|`SessionId`|Dieses Feld wird intern von EOP verwendet.|
|`AppId`|Dieses Feld wird intern von EOP verwendet.|
|`ClientAppId`|Dieses Feld wird intern von EOP verwendet.|
|`Identity`|Dieses Feld wird intern von EOP verwendet.|
|`IsValid`|Dieses Feld wird intern von EOP verwendet.|
|`ObjectState`|Dieses Feld wird intern von EOP verwendet.|
|
