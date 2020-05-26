---
title: Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratoren können erfahren, wie Sie das Administrator-Überwachungsprotokoll in eigenständiger Exchange Online Schutz (EoP) anzeigen und durchsuchen.
ms.openlocfilehash: b3f2f2601be1ce6e2120b60d23f617ae4e174e08
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351861"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Anzeigen des Administratorüberwachungsprotokolls in EOP als eigenständige Lösung

In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die Exchange-Verwaltungskonsole (EAC) oder die eigenständige EoP-PowerShell verwenden, um nach Einträgen im Administrator-Überwachungsprotokoll zu suchen und diese anzuzeigen.

Das administratorüberwachungsprotokoll zeichnet bestimmte Aktionen auf der Grundlage von eigenständigen EoP PowerShell-Cmdlets auf, die von Administratoren und Benutzern ausgeführt wurden, denen Administratorrechte zugewiesen wurden. Mit Einträgen im Administrator-Überwachungsprotokoll erhalten Sie Informationen dazu, welches Cmdlet ausgeführt wurde, welche Parameter verwendet wurden, wer das Cmdlet ausgeführt hat und welche Objekte betroffen sind.

> [!NOTE]
> <ul><li>Die Administrator Überwachungsprotokollierung ist standardmäßig aktiviert und kann nicht deaktiviert werden.</li><li>Das administratorüberwachungsprotokoll zeichnet keine Aktionen basierend auf Cmdlets auf, die mit dem Verb **Get**, der **Suche**oder dem **Test**beginnen.</li><li>Die Überwachungsprotokolleinträge werden 90 Tage lang aufbewahrt. Wenn ein Eintrag älter als 90 Tage ist, wird er gelöscht.</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Überwachungsprotokolle oder die Rolle "Überwachungsprotokolle nur anzeigen", die standardmäßig den Rollengruppen ComplianceManagement, Mitglied (globale Administratoren) und SecurityAdministrator zugewiesen sind. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Anzeigen des administratorüberwachungsprotokolls mithilfe der Exchange-Verwaltungskonsole

1. Wechseln Sie in der Exchange- **Verwaltungskonsole zu Compliance Management** \> **Auditing**, und wählen Sie dann **Administrator-Überwachungsprotokollbericht ausführen**aus.

2. Wählen Sie auf der Seite nach **Änderungen an Administratorrollengruppen suchen** , die geöffnet wird, ein **Start Datum** und ein **Enddatum** aus (der Standardbereich ist die letzten zwei Wochen), und wählen Sie dann **Suchen**aus. Sämtliche Konfigurationsänderungen, die im angegebenen Zeitraum erfolgt sind, werden angezeigt und können anhand der folgenden Informationen sortiert werden:

   - **Date**: das Datum und die Uhrzeit, zu der die Konfigurationsänderung vorgenommen wurde. Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.

   - **Cmdlet**: der Name des Cmdlets, das zum vornehmen der Konfigurationsänderung verwendet wurde.

   - **User**: der Name des Benutzerkontos des Benutzers, der die Konfigurationsänderung vorgenommen hat.

     Es können bis zu 5000 Einträge auf mehreren Seiten angezeigt werden. Geben Sie einen kürzeren Datumsbereich ein, wenn Sie Ihre Ergebnisse eingrenzen möchten. Wenn Sie ein einzelnes Suchergebnis auswählen, werden im Detailbereich die folgenden weiteren Informationen angezeigt:

   - **Objekt geändert**: das Objekt, das vom Cmdlet geändert wurde.

   - **Parameter (Parameter: Wert)**: die verwendeten Cmdlet-Parameter und der mit dem Parameter angegebene Wert.

3. Wenn Sie einen bestimmten Überwachungsprotokolleintrag drucken möchten, klicken Sie im Detailbereich auf die Schaltfläche **Drucken**.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Verwenden eigenständiger EoP PowerShell zum Anzeigen des administratorüberwachungsprotokolls

Sie können eigenständige EoP PowerShell verwenden, um nach Überwachungsprotokolleinträgen zu suchen, die die von Ihnen angegebenen Kriterien erfüllen. Verwenden Sie die folgende Syntax:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Hinweise**:

- Sie können den Parameter _para_ meters nur zusammen mit dem _Cmdlets_ -Parameter verwenden.

- Der Parameter _ObjectIDs_ filtert die Ergebnisse nach dem Objekt, das vom Cmdlet geändert wurde. Ein gültiger Wert hängt davon ab, wie das Objekt im Überwachungsprotokoll dargestellt wird. Zum Beispiel:

  - Name
  - Kanonischer Distinguished Name (beispielsweise contoso.com/users/Akia Al-Zuhairi)

  Sie müssen wahrscheinlich andere Filterparameter für dieses Cmdlet verwenden, um die Ergebnisse einzugrenzen und die Objekttypen zu identifizieren, an denen Sie interessiert sind.

- Der Parameter _userids_ filtert die Ergebnisse des Benutzers, der die Änderung vorgenommen hat (der das Cmdlet ausgeführt hat).

- Wenn Sie für die Parameter _StartDate_ und _EndDate_ einen Datum/Uhrzeit-Wert ohne Zeitzone angeben, wird der Wert in koordinierter Weltzeit (Coordinated Universal Time, UTC) angegeben. Verwenden Sie eine der folgenden Optionen, um einen Datum/Uhrzeit-Wert für diesen Parameter anzugeben:

  - Datum/Uhrzeit-Wert in UTC, z. B.: "2016-05-06 14:30:00z".

  - Geben Sie den Wert für Datum/Uhrzeit als Formel an, die das Datum/die Uhrzeit in Ihrer lokalen Zeitzone in UTC konvertiert: beispielsweise `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Weitere Informationen finden Sie unter [Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313).

- Das Cmdlet gibt standardmäßig maximal 1.000 Protokolleinträge zurück. Verwenden Sie den _resultse_ -Parameter, um bis zu 250.000 Protokolleinträge anzugeben. Oder verwenden Sie den Wert `Unlimited` , um alle Einträge zurückzugeben.

In diesem Beispiel wird eine Suche nach allen Überwachungsprotokolleinträgen ausgeführt, welche die folgenden Kriterien erfüllen:

- **Start Datum**: 4. August 2019
- **Ende Datum**: 3. Oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Anzeigen der Details von Überwachungsprotokolleinträgen

Das Cmdlet **Search-AdminAuditLog** gibt die Felder zurück, die im Abschnitt [Überwachungsprotokoll Inhalt](#audit-log-contents) weiter unten in diesem Thema beschrieben werden. Von den vom Cmdlet zurückgegebenen Feldern enthalten zwei Felder, **CmdletParameters** und **ModifiedProperties**, zusätzliche Informationen, die standardmäßig nicht zurückgegeben werden.

Führen Sie die folgenden Schritte aus, um die Inhalte der Felder **CmdletParameters** und **ModifiedProperties** anzuzeigen.

1. Legen Sie die Suchkriterien fest, führen Sie das Cmdlet **Search-AdminAuditLog** aus, und speichern Sie die Ergebnisse über den folgenden Befehl in einer Variablen.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Jeder Überwachungsprotokolleintrag wird als Arrayelement in der Variablen gespeichert `$Results` . Zur Auswahl eines Arrayelements geben Sie den Arrayelementindex an. Arrayelementindizes beginnen für das erste Arrayelement bei 0. Verwenden Sie beispielsweise den folgenden Befehl, um das fünfte Arrayelement (mit dem Index 4) abzurufen.

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

|||
|---|---|
|**Field**|**Beschreibung**|
|`RunspaceId`|Dieses Feld wird intern von EoP verwendet.|
|`ObjectModified`|Dieses Feld enthält das Objekt, das von dem im Feld angegebenen Cmdlet geändert wurde `CmdletName` .|
|`CmdletName`|Dieses Feld enthält den Namen des Cmdlets, das vom Benutzer im Feld ausgeführt wurde `Caller` .|
|`CmdletParameters`|Dieses Feld enthält die Parameter, die beim Ausführen des Cmdlets im `CmdletName` Feld angegeben wurden. In diesem Feld wird auch, falls vorhanden, der in diesem Parameter angegebene Wert gespeichert, er wird jedoch nicht in der Standardausgabe angezeigt.|
|`ModifiedProperties`|Dieses Feld enthält die Eigenschaften, die für das Objekt in dem Feld geändert wurden `ObjectModified` . In diesem Feld werden auch der alte Wert der Eigenschaft und der neue gespeicherte Wert gespeichert, sie werden jedoch nicht in der Standardausgabe angezeigt.|
|`Caller`|Dieses Feld enthält das Benutzerkonto des Benutzers, der das Cmdlet im Feld ausgeführt hat `CmdletName` .|
|`ExternalAccess`|Dieses Feld wird intern von EoP verwendet.|
|`Succeeded`|Dieses Feld gibt an, ob das Cmdlet im `CmdletName` Feld erfolgreich ausgeführt wurde. Der Wert ist entweder `True` oder `False` .|
|`Error`|Dieses Feld enthält die Fehlermeldung, die generiert wird, wenn das Cmdlet im `CmdletName` Feld nicht erfolgreich abgeschlossen wurde.|
|`RunDate`|Dieses Feld enthält das Datum und die Uhrzeit, zu der das Cmdlet im `CmdletName` Feld ausgeführt wurde. Datum und Uhrzeit werden im UTC-Format (Coordinated Universal Time, koordinierte Weltzeit) gespeichert.|
|`OriginatingServer`|Dieses Feld gibt den Server an, auf dem das im Feld angegebene Cmdlet `CmdletName` ausgeführt wurde.|
|`ClientIP`|Dieses Feld wird intern von EoP verwendet.|
|`SessionId`|Dieses Feld wird intern von EoP verwendet.|
|`AppId`|Dieses Feld wird intern von EoP verwendet.|
|`ClientAppId`|Dieses Feld wird intern von EoP verwendet.|
|`Identity`|Dieses Feld wird intern von EoP verwendet.|
|`IsValid`|Dieses Feld wird intern von EoP verwendet.|
|`ObjectState`|Dieses Feld wird intern von EoP verwendet.|
|
