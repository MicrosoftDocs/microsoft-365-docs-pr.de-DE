---
title: Benennungsrichtlinie für Office 365-Gruppen
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Erfahren Sie, wie eine Benennungsrichtlinie für Office 365-Gruppen erstellt wird.
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241394"
---
# <a name="office-365-groups-naming-policy"></a>Benennungsrichtlinie für Office 365-Gruppen

Mithilfe der Gruppenbenennungsrichtlinie können Sie eine konsistente Benennungsstrategie für Gruppen erzwingen, die von Benutzern in Ihrer Organisation erstellt werden. Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

Die Benennungsrichtlinie wird übergreifend auf Gruppen angewendet, die in allen Workloads (wie Outlook, Microsoft Teams, SharePoint, Planner, Yammer usw.) erstellt werden. Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.

> [!TIP]
> Die Benennungsrichtlinie für Office 365-Gruppen gilt nur für Office 365-Gruppen. Sie gilt nicht für in Exchange Online erstellte Verteilergruppen. Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:

- **Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu\_definieren\_(Beispiel\_: "GRP US My Group Engineering"). Bei den Präfixen/Suffixen kann es sich entweder um feste Zeichenfolgen oder Benutzerattribute wie [Department] handeln, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.

- **Benutzerdefinierte blockierte Wörter**: Sie können eine Gruppe blockierter Wörter für Ihre Organisation hochladen, die in von Benutzern erstellten Gruppen blockiert würde. (Beispiel: "CEO, Abrechnung, HR").

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Die Verwendung der Azure AD-Benennungsrichtlinie für Office 365-Gruppen setzt voraus, dass Sie über eine Azure Active Directory Premium P1-Lizenz oder eine Azure AD Basic EDU-Lizenz für jeden eindeutigen Benutzer (einschließlich Gäste) verfügen, der Mitglied einer oder mehrerer Office 365-Gruppen ist.
Dies gilt auch für den Administrator, der die Benennungsrichtlinie für Gruppen erstellt.

## <a name="prefix-suffix-naming-policy"></a>Präfix Suffix-Benennungsrichtlinie

Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.

### <a name="fixed-strings"></a>Feste Zeichenfolgen

Sie können kurze Zeichenfolgen verwenden, mit denen Sie Gruppen in der GAL und im linken Navigationsbereich der Gruppen Arbeitsauslastungen unterscheiden können. Einige der gängigen Präfix Suffixe sind Schlüsselwörter wie "GRP\_Name", "\#Name", "\_Name".

### <a name="attributes"></a>Attribute

Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".

|||
|:-----|:-----|
|**Beispiele**|Richtlinie = "GRP [Gruppenname] [Abteilung]"|
||Abteilung des Benutzers = Entwicklung|
||Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"|

Die unterstützten Azure Active Directory (Azure AD)-Attribute sind [Abteilung], [Firma], [Büro], [Bundesland/Kanton], [Land/Region], [Position]

- Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen angesehen. Z. B. "[Postleitzahl]"

- Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.

Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.

### <a name="things-to-look-out-for"></a>Worauf Sie achten sollten

- Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.

- Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden. Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppenalias nicht zulässig sind, werden diese entfernt und die Präfixe und Suffixe dann auf den Gruppenalias angewendet. In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.

- Wenn Sie jammern Office 365 verbundene Gruppen verwenden, vermeiden Sie die Verwendung der folgenden Zeichen in ihrer Benennungs \#Richtlinie \[: \]@ \<,, \>,, und. Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.

## <a name="custom-blocked-words"></a>Benutzerdefinierte blockierte Wörter

Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.

Die Überprüfung von blockierten Wörtern wird für den eingegebenen Gruppennamen durchgeführt. Wenn der Benutzer also "darnit" eingibt und\_"prefix" die Benennungsrichtlinie\_ist, schlägt "prefix darnit" fehl.

Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen. Es erfolgt keine Suche nach Teilzeichenfolgen, sodass Benutzer ein Wort wie 'Klarschiff' verwenden können, obwohl 'Arsch' ein blockiertes Wort ist.

**Dinge, die Sie beachten**sollten:

- Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.

- Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.

- Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.

- Es können maximal 5.000 Wörter als blockierte Wörter festgelegt werden.

## <a name="admin-override"></a>Außerkraftsetzung durch Administratoren

Ausgewählte Administratoren sind übergreifend über alle Workloads und Endpunkte von diesen Richtlinien ausgenommen, sodass sie Gruppen mit den blockierten Wörtern und Benennungskonventionen nach eigenen Wünschen erstellen können. Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.

- Globaler Administrator

- Partnersupport der Ebene 1

- Partnersupport der Ebene 2

- Administrator für Benutzerkonten

- Verzeichnisautoren

## <a name="how-to-set-up-the-naming-policy"></a>Vorgehensweise zum Einrichten der Benennungsrichtlinie

So richten Sie eine Benennungsrichtlinie ein:

1. Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com) unter **Verwalten** auf **Gruppen**.
2. Klicken Sie unter **Einstellungen** auf **Benennungsrichtlinie**.
3. Wählen Sie die Registerkarte **Gruppenbenennungsrichtlinie** aus.
4. Wählen Sie unter **Aktuelle Richtlinie** aus, ob ein Präfix oder ein Suffix oder beides benötigt wird, und aktivieren Sie die entsprechenden Kontrollkästchen.
5. Wählen Sie zwischen **Attribut** und **Zeichenfolge** für jede Zeile aus, und geben Sie dann das Attribut oder die Zeichenfolge an.
6. Wenn Sie die benötigten Präfixe und Suffixe hinzugefügt haben, klicken Sie auf **Speichern**.

![Screenshot der Einstellungen für Benennungsrichtlinien für Gruppen in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a>Benutzererfahrung der Benennungsrichtlinien in den einzelnen Office 365-Apps

Die Office 365-Apps wurden aktualisiert, um eine Vorschau des Benennungsrichtlinien-Gruppennamens (mit Präfixen und Suffixen) anzuzeigen, wenn der Benutzer den Gruppennamen und den Alias eingibt. Wenn Benutzer blockierte Wörter eingeben, wird eine Fehlermeldung angezeigt, sodass sie die blockierten Wörter entfernen können.

## <a name="outlook-on-the-web"></a>Outlook im Web

Outlook im Internet (früher bekannt als Outlook Web App oder OWA) zeigt den Benennungsrichtlinien ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder Gruppen Alias eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird in der Benutzeroberfläche eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann. Im folgenden sind die Snapshots für Outlook im Webbrowser dargestellt.

![Nebeneinander angeordnete Ansicht von Gruppenbenennungsrichtlinien in Office 365-Gruppen](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a>Outlook Desktop

In Outlook Desktop erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel. Die Outlook Desktop-App zeigt derzeit noch keine Vorschau der Benennungsrichtlinie an und gibt Fehler aufgrund benutzerdefinierter blockierter Wörter nicht zurück, wenn der Benutzer den Gruppennamen eingibt. Allerdings wird die Benennungsrichtlinie beim Auswählen von Erstellen/Bearbeiten automatisch angewendet, und Benutzern werden Fehler angezeigt, wenn sich im Gruppennamen oder Alias benutzerdefinierte blockierte Wörter befinden.

## <a name="microsoft-teams"></a>Microsoft Teams

Wenn der Benutzer einen Teamnamen eingibt, zeigt Microsoft Teams den von der Benennungsrichtlinie ergänzten Namen an. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.

![Gruppenbenennungsrichtlinie in Microsoft Teams, blockiertes Beispiel](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a>SharePoint

SharePoint zeigt den Namen gemäß der Benennungsrichtlinie an, wenn der Benutzer einen Websitenamen oder eine Gruppen-E-Mail-Adresse eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung zusammen mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.

![Gruppenbenennungsrichtlinie – Blockierter Name einer SharePoint-Website](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a>Microsoft Stream

Microsoft Stream zeigt den gemäß der Benennungsrichtlinie ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder einen Gruppen-E-Mail-Alias eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung mit dem blockierten Wort angezeigt, sodass der Benutzer es entfernen kann.

![Gruppenbenennungsrichtlinie, blockiertes Beispiel für Microsoft Stream](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a>Outlook iOS- und Android-App

In Outlook-Apps erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel. Outlook Mobile zeigt bei der Eingabe des Gruppennamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen der Gruppe eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.

## <a name="planner"></a>Planner

Planer ist mit den Benennungsrichtlinien kompatibel. Planner zeigt bei der Eingabe des Plannamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen des Plans eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.

![Gruppenbenennungsrichtlinie – "Neuen Plan erstellen", blockiertes Beispiel](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a>Dynamics 365 for Customer Engagement

Dynamics 365 for Customer Engagement ist mit der Benennungsrichtlinie konform. Dynamics 365 zeigt den durch die Benennungsrichtlinie ergänzten Namen an, wenn der Benutzer einen Gruppennamen oder den E-Mail-Alias einer Gruppe eingibt. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird eine Fehlermeldung mit dem blockierten Wort angezeigt, damit der Benutzer es entfernen kann.

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a>School Data Sync (SDS)

Mithilfe von SDS erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, die Benennungsrichtlinie wird aber nicht automatisch angewendet. SDS-Administratoren müssen die Präfixe und Suffixe an die Namen von Klassen anhängen, für die Gruppen erstellt werden müssen, und sie dann auf SDS hochladen. Andernfalls tritt beim Erstellen/Bearbeiten von Gruppen ein Fehler auf.

## <a name="outlook-customer-manager-ocm"></a>Outlook Customer Manager (OCM)

Outlook Customer Manager ist mit der Benennungsrichtlinie konform. Die Benennungsrichtlinie wird automatisch auf die in Outlook Customer Manager erstellte Gruppe angewendet. Wenn eines der Wörter in "Gesamtes Vertriebsteam" als benutzerdefiniertes blockiertes Wort definiert ist, wird die Gruppenerstellung in OCM blockiert. Der Benutzer kann die OCM-Gruppe nicht erstellen und wird für die Nutzung der OCM-App blockiert.

## <a name="classroom-app"></a>Classroom-App

In der Classroom-App erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, aber die Benennungsrichtlinie wird nicht automatisch angewendet, und beim Eingeben eines Classroom-Gruppennamens wird den Benutzern keine Vorschau der Benennungsrichtlinie angezeigt. Daher müssen Benutzer den um Präfixe und Suffixe ergänzten Gruppennamen eingeben. Andernfalls treten beim Erstellen oder Bearbeiten der Classroom-Gruppe Fehler auf.

## <a name="power-bi"></a>Power BI

In Power BI-Arbeitsbereichen erstellte Gruppen sind mit der Benennungsrichtlinie kompatibel, die Benennungsrichtlinie wird aber nicht automatisch angewendet. Und die Vorschau der Benennungsrichtlinie wird Benutzern nicht angezeigt, wenn Sie einen Power BI-Arbeitsbereichsnamen eingeben.

Der empfohlene Name – mit der angewendeten Benennungsrichtlinie – wird in den Fehlerdetails unter Erstellen oder Bearbeiten von Arbeitsbereichen angezeigt. Benutzer müssen dann den ergänzten Arbeitsbereichsnamen mit Präfixen und Suffixen eingeben. Andernfalls treten beim Erstellen oder Bearbeiten des Arbeitsbereichs Fehler auf.

## <a name="yammer"></a>Yammer

Wenn ein Benutzer, der sich mit seinem Azure Active Directory-Konto bei Yammer angemeldet hat, eine Gruppe erstellt oder einen Gruppennamen bearbeitet, entspricht der Gruppenname der Benennungsrichtlinie. Dies gilt sowohl für mit Office 365 verbundene Gruppen als auch für alle anderen Yammer-Gruppen.

Wenn eine mit Office 365 verbundene Gruppe erstellt wurde, bevor die Benennungsrichtlinie vorhanden war, entspricht der Gruppenname nicht automatisch den Benennungsrichtlinien. Wenn ein Benutzer den Gruppennamen bearbeitet, wird er aufgefordert, das Präfix und das Suffix hinzuzufügen.

Wenn die Benennungsrichtlinie Zeichen enthält, die nicht in Yammer-Gruppennamen enthalten sein dürfen, können nur Administratoren eine verbundene Gruppe in Yammer erstellen.

## <a name="staffhub"></a>StaffHub

StaffHub-Teams unterliegen nicht der Benennungsrichtlinie, die zugrunde liegende Office 365-Gruppe jedoch schon. Der StaffHub-Teamname wendet die Präfixe und Suffixe nicht an und wird nicht auf benutzerdefinierte blockierte Wörter überprüft. StaffHub wendet die Präfixe und Suffixe allerdings auf die zugrunde liegende Office 365-Gruppe an und entfernt dort ggf. blockierte Wörter.

## <a name="exchange-powershell"></a>Exchange PowerShell

Exchange-PowerShell-Cmdlets sind mit der Benennungsrichtlinie kompatibel. Benutzern werden entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.

## <a name="azure-active-directory-powershell-cmdlets"></a>Azure Active Directory PowerShell-Cmdlets

Azure Active Directory PowerShell-Cmdlets sind mit der Benennungsrichtlinie konform. Benutzern werden entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.

## <a name="exchange-admin-center"></a>Exchange Admin Center

Das Exchange Admin Center (EAC) ist mit der Benennungsrichtlinie kompatibel. Beim Erstellen oder Bearbeiten von Aktionen werden Benutzern entsprechende Fehlermeldungen mit Vorschlägen für Präfixe und Suffixe und benutzerdefinierte blockierte Wörter angezeigt, wenn die Benennungskonvention in Gruppennamen und Gruppenaliasen nicht befolgt wird.

## <a name="microsoft-365-admin-center"></a>Microsoft 365 Admin Center

Das Microsoft 365 Admin Center ist mit den Benennungsrichtlinien kompatibel. Beim Erstellen oder Bearbeiten von Aktionen wird die Benennungsrichtlinie automatisch angewendet. Benutzer erhalten entsprechende Fehler, wenn sie benutzerdefinierte blockierte Wörter eingeben. Das Microsoft 365 Admin Center zeigt derzeit noch keine Vorschau der Benennungsrichtlinie an und gibt die Fehler aufgrund benutzerdefinierter blockierter Wörter nicht zurück, wenn der Benutzer den Gruppennamen eingibt.

## <a name="azure-active-directory-portal"></a>Azure Active Directory-Portal

Das Azure Active Directory-Portal ist mit der Benennungsrichtlinie konform. Das Azure Active Directory-Portal zeigt bei der Eingabe des Gruppennamens eine Vorschau des durch die Benennungsrichtlinie erzwungenen Namens an. Wenn ein Benutzer ein benutzerdefiniertes blockiertes Wort eingibt, wird beim Erstellen der Gruppe eine Fehlermeldung angezeigt, sodass der Benutzer das blockierte Wort entfernen kann.

## <a name="more-articles-on-naming-policy"></a>Weitere Artikel zur Benennungsrichtlinie

[Erzwingen einer Benennungsrichtlinie für Office 365-Gruppen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?linkid=868341)
