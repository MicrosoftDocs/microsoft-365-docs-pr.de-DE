---
title: Verwalten einer Multi-Geo-Umgebung
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Administratoren erfahren, wie sie SharePoint und OneDrive Dienste in einer Multi-Geo-Umgebung verwalten.
ms.openlocfilehash: 4c5215b855b8ca1840035b39fcfbddde419c13d8
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362318"
---
# <a name="administering-a-multi-geo-environment"></a>Verwalten einer Multi-Geo-Umgebung

Hier sehen Sie, wie Microsoft 365-Dienste in einer Umgebung mit mehreren geografischen Standorten funktionieren.

## <a name="administrator-experience"></a>Administratorerfahrung

Das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint) verfügt über eine Registerkarte **"Geografische Standorte"** in der linken Navigationsleiste, die eine Karte mit geografischen Standorten enthält, auf der Sie Ihre geografischen Standorte anzeigen und verwalten können. Verwenden Sie diese Seite, um geografische Standorte für Ihren Mandanten hinzuzufügen oder zu löschen.

## <a name="audit-log-search"></a>Durchsuchen von Überwachungsprotokollen

Ein einheitliches [Überwachungsprotokoll](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) für alle Nebenstandorte steht auf der Suchseite des Microsoft 365-Überwachungsprotokolls zur Verfügung. Sie können alle Überwachungsprotokolleinträge für alle geografischen Standorte anzeigen. Beispiel: Sie können Benutzeraktivitäten für die geografischen Standorte NAM und EUR in einer Organisationsansicht anzeigen und dann vorhandene Filter anwenden, um bestimmte Benutzeraktivitäten anzuzeigen.

## <a name="bcs-secure-store-apps"></a>BCS, Secure Store, Apps

BCS, Secure Store und Apps verfügen über separate Instanzen. Daher sollte der SharePoint Online-Administrator diese Dienste von dem jeweiligen Satellitenstandort aus separat verwalten und konfigurieren.

## <a name="compliance-admin-center"></a>Compliance Admin Center

Es gibt ein zentrales Compliance Center für einen Multi-Geo-Mandanten: [Microsoft 365 Compliance Admin Center.](https://compliance.microsoft.com/)

## <a name="ediscovery"></a>eDiscovery

Standardmäßig kann ein eDiscovery-Manager oder ein Administrator eines Mandanten mit mehreren geografischen Standorten eDiscovery nur am zentralen Standort des Mandanten durchführen. Der globale Office 365-Administrator muss eDiscovery-Managerberechtigungen zuweisen, damit andere Personen eDiscovery durchführen können, und einen "Region"-Parameter im entsprechenden Compliancesicherheitsfilter zuweisen, um die Region zum Durchführen von eDiscovery als Satellitenstandort festzulegen. Andernfalls wird eDiscovery nicht für den Satellitenstandort durchgeführt werden. Informationen zum Konfigurieren des Compliancesicherheitsfilters für eine Region finden Sie unter [Konfigurieren von Office 365-Multi-Geo eDiscovery](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Exchange-Postfächer

Exchange-Postfächer von Benutzern werden automatisch verschoben, wenn sich ihr PDL ändert. Wenn ein neues Postfach erstellt wird, wird es dem PDL des Benutzers oder an einem zentralen Standort bereitgestellt, wenn kein Wert für den PDL des Benutzers festgelegt wurde.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) für Information Protection (IP)

Sie können Ihre IP-DLP-Richtlinien für OneDrive for Business, SharePoint und Exchange im Security and Compliance Center festlegen und die Richtlinien wie erforderlich auf den gesamten Mandanten oder auf bestimmte Benutzer anwenden. Beispiel: Wenn Sie eine Richtlinie für einen Benutzer an einem Satellitenstandort auswählen möchten, wählen Sie aus, dass die Richtlinie auf einen bestimmten OneDrive angewendet werden soll, und geben Sie OneDrive-URL des Benutzers ein. Eine Anleitung zum Erstellen von DLP-Richtlinien finden Sie in der [Übersicht über DLP-Richtlinien](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e).

Die DLP-Richtlinien werden automatisch basierend auf ihrer Anwendbarkeit auf den jeweiligen geografischen Standort synchronisiert.

Die Implementierung von IP- (Information Protection) und DLP-Richtlinien für alle Benutzer an einem geografischen Standort steht nicht als Option in der Benutzeroberfläche zur Verfügung. Sie müssen stattdessen die entsprechenden Konten für die Richtlinie auswählen oder die Richtlinie global auf alle Konten anwenden.

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

Für den Satellitenstandort erstellte PowerApps verwenden den Endpunkt, der sich am zentralen Standort des Mandanten befindet. Microsoft PowerApps ist kein Dienst, der auf mehrfache geografische Standorte ausgelegt ist. 

## <a name="power-automate"></a>Power Automate

Für den Satellitenstandort erstellte Flows verwenden den Endpunkt, der sich am standardmäßigen geografischen Standort für den Mandanten befindet.  Power Automate ist kein Multi-Geo-Dienst. 

## <a name="sharepoint-storage-quota"></a>SharePoint-Speicherkontingent

Alle geografischen Standorte einer Multi-Geo-Umgebung teilen sich das Speicherkontingent des Mandanten.  Sie können das Speicherkontingent auch verwalten, indem Sie ein bestimmtes Kontingent für einen bestimmten geografischen Standort reservieren. Weitere Informationen finden Sie unter [SharePoint Speicherkontingente in Multi-Geo-Umgebungen](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Freigabe

Administratoren können Freigaberichtlinien für die einzelnen Standorte einrichten und verwalten. Die OneDrive- und SharePoint-Websites an den einzelnen geografischen Standorten richten sich nur nach den jeweiligen Freigabeeinstellungen, die für den Standort festgelegt wurden. (Sie können z. B. die [externe Freigabe](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) für Ihren zentralen Standort zulassen, jedoch nicht für den Satellitenstandort, und umgekehrt.) Beachten Sie, dass die Freigabeeinstellungen keine Konfiguration von Freigabeeinschränkungen zwischen den geografischen Standorten zulassen.

## <a name="stream"></a>Stream

In Stream hochgeladene Videos werden im OneDrive der Person gespeichert, die hochgeladen hat. Besprechungsaufzeichnungen werden im OneDrive jedes Teilnehmers gespeichert, der die Besprechung aufzeichnet.

## <a name="taxonomy"></a>Taxonomie

Wir unterstützen eine einheitliche [Taxonomie](/sharepoint/managed-metadata) für vom Unternehmen verwaltete Metadaten über geografische Standorte hinweg, wobei der Master am zentralen Standort Ihres Unternehmens gehostet wird. Wir empfehlen, dass Sie die globale Taxonomie vom zentralen Standort aus verwalten und nur standortspezifische Ausdrücke zur Taxonomie der Satellitenstandorte hinzufügen. Ausdrücke der globalen Taxonomie werden mit den Satellitenstandorten synchronisiert.

Weitere Informationen und Anleitungen für Entwickler finden Sie unter [Verwalten von Metadaten in einem Multi-Geo-Mandanten](/sharepoint/dev/solution-guidance/multigeo-managedmetadata).

## <a name="user-profile-application"></a>Benutzerprofilanwendung

Es gibt eine [Benutzerprofilanwendung](/sharepoint/manage-user-profiles) an jedem geografischen Standort. Profilinformationen der Benutzer werden an dem jeweiligen geografischen Standort gehostet und stehen dem Administrator für diesen geografischen Standort zur Verfügung.

Wenn Sie über benutzerdefinierte Profileigenschaften verfügen, wird empfohlen, dasselbe Profilschema für alle geografischen Standorte zu verwenden und die benutzerdefinierten Profileigenschaften entweder für alle oder bestimmte geografischen Standorte aufzufüllen. Eine Anleitung dazu, wie Sie Benutzerprofildaten programmgesteuert auffüllen, finden Sie unter [API für die Massenaktualisierung von Benutzerprofilen](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Weitere Informationen und Anleitungen für Entwickler finden Sie unter [Verwenden von Profilen in einem Multi-Geo-Mandanten](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience).

## <a name="yammer"></a>Yammer

Yammer ist keine Multi-Geo-Arbeitsauslastung. Yammer in Yammer gespeicherten Threads werden am zentralen Standort des Mandanten platziert. Yammer führt eine Dateispeicheränderung aus, die Yammer Dateien in SharePoint speichert. Yammer in SharePoint gespeicherten Dateien wird die SharePoint Website platziert, die der Yammer Gruppe zugeordnet ist. SharePoint Gruppenwebsites basieren auf der PDL-Logik, wie in [SharePoint Websites und Gruppen](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)beschrieben.