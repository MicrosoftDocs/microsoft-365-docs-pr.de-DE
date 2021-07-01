---
title: Microsoft 365 Identitätsmodelle und Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Erfahren Sie, wie Sie den Azure AD-Benutzeridentitätsdienst in Microsoft 365 mithilfe von reinen Cloud- oder Hybrididentitätsmodellen verwalten.
ms.openlocfilehash: 93a37f39a4d96d7c2e434ed6edf4df588e672a0f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228495"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 Identitätsmodelle und Azure Active Directory

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 verwendet Azure Active Directory (Azure AD), einen cloudbasierten Benutzeridentitäts- und Authentifizierungsdienst, der in Ihrem Microsoft 365-Abonnement enthalten ist, um Identitäten und Authentifizierung für Microsoft 365 zu verwalten. Die richtige Konfiguration Ihrer Identitätsinfrastruktur ist für die Verwaltung Microsoft 365 Benutzerzugriffs und der Berechtigungen für Ihre Organisation von entscheidender Bedeutung.

Bevor Sie beginnen, schauen Sie sich dieses Video an, um eine Übersicht über die Identitätsmodelle und Authentifizierung für Microsoft 365 zu erhalten.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Ihre erste Wahl bei der Planung ist das Microsoft 365 Identitätsmodell.

## <a name="microsoft-365-identity-models"></a>Microsoft 365 Identitätsmodelle

Um Benutzerkonten zu planen, müssen Sie zunächst die beiden Identitätsmodelle in Microsoft 365 verstehen. Sie können die Identitäten Ihrer Organisation nur in der Cloud verwalten, oder Sie können Ihre lokalen AD DS-Identitäten (Active Directory Domain Services) verwalten und diese zur Authentifizierung verwenden, wenn Benutzer auf Microsoft 365-Clouddienste zugreifen.

Nachfolgend finden Sie die beiden Identitätstypen sowie deren beste Anwendungsfälle und Vorteile.

| Attribut | Reine Cloudidentität | Hybrididentität |
|:-------|:-----|:-----|
| **Definition** | Das Benutzerkonto ist nur im Azure AD-Mandanten für Ihr Microsoft 365-Abonnement vorhanden. | Ein Benutzerkonto ist in AD DS vorhanden, und eine Kopie befindet sich auch im Azure AD-Mandanten für Ihr Microsoft 365-Abonnement. Das Benutzerkonto in Azure AD kann auch eine Hashversion des bereits gehashten AD DS-Benutzerkontokennworts enthalten. |
| **Authentifizierung von Benutzeranmeldeinformationen durch Microsoft 365** | Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement führt die Authentifizierung mit dem Cloudidentitätskonto durch. | Der Azure AD-Mandant für Ihr Microsoft 365-Abonnement behandelt verarbeitet entweder den Authentifizierungsprozess oder leitet den Benutzer an einen anderen Identitätsanbieter weiter. |
| **Ideal für** | Organisationen, die keinen lokalen AD DS besitzen oder benötigen. | Organisationen, die AD DS oder einen anderen Identitätsanbieter verwenden. |
| **Größter Vorteil** | Einfach zu verwenden. Es sind keine zusätzlichen Verzeichnistools oder Server erforderlich. | Benutzer können dieselben Anmeldeinformationen verwenden, wenn sie auf lokale oder cloudbasierte Ressourcen zugreifen. |
||||

## <a name="cloud-only-identity"></a>Reine Cloudidentität

Bei der reinen Cloudidentität werden Benutzerkonten verwendet, die nur in Azure AD vorhanden sind. Reine Cloudidentität wird in der Regel von kleinen Organisationen verwendet, die nicht über lokale Server verfügen oder AD DS nicht zum Verwalten lokaler Identitäten verwenden.

Hier sind die grundlegenden Komponenten der reinen Cloudidentität.

![Grundlegende Komponenten der reinen Cloudidentität](../media/about-microsoft-365-identity/cloud-only-identity.png)

Sowohl lokale als auch Remotebenutzer (Onlinebenutzer) verwenden ihre Azure AD-Benutzerkonten und Kennwörter, um auf Microsoft 365 Clouddienste zuzugreifen. Azure AD authentifiziert Benutzeranmeldeinformationen basierend auf den gespeicherten Benutzerkonten und Kennwörtern.

### <a name="administration"></a>Verwaltung
Da Benutzerkonten nur in Azure AD gespeichert sind, verwalten Sie Cloudidentitäten mit Tools wie [Microsoft 365 Admin Center](../admin/add-users/index.yml) und [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

## <a name="hybrid-identity"></a>Hybrididentität

Die Hybrididentität verwendet Konten, die von einem lokalen AD DS stammen und eine Kopie im Azure AD-Mandanten eines Microsoft 365-Abonnements aufweisen. Die meisten Änderungen fließen jedoch nur in eine Richtung. Änderungen, die Sie an AD DS-Benutzerkonten vornehmen, werden mit Ihrer Kopie in Azure AD synchronisiert. Änderungen, die in cloudbasierten Konten in Azure AD vorgenommen wurden, wie z. B. neue Benutzerkonten, werden jedoch nicht mit AD DS synchronisiert.

Azure AD Connect bietet die laufende Kontosynchronisierung. Es wird auf einem lokalen Server ausgeführt, überprüft auf Änderungen in AD DS und leitet diese Änderungen an Azure AD weiter. Azure AD Connect bietet die Möglichkeit zu filtern, welche Konten synchronisiert werden, und ob eine Hashversion der Benutzerkennwörter synchronisiert werden soll; dies wird als „Kennworthashsynchronisierung“ (Password hash synchronization, PHS) bezeichnet.

Wenn Sie die Hybrididentität implementieren, ist Ihr lokales AD DS die autorisierende Quelle für Kontoinformationen. Dies bedeutet, dass Sie Verwaltungsaufgaben hauptsächlich lokal durchführen, die dann mit Azure AD synchronisiert werden.

Nachfolgend finden Sie die Komponenten der Hybrididentität.

![Komponenten der Hybrididentität](../media/about-microsoft-365-identity/hybrid-identity.png)

Der Azure AD-Mandant hat eine Kopie der AD DS-Konten. In dieser Konfiguration authentifizieren sich sowohl lokale als auch Remotebenutzer beim Zugriff auf Microsoft 365-Clouddienste bei Azure AD.

> [!NOTE]
> Sie müssen immer Azure AD Connect verwenden, um Benutzerkonten für die Hybrididentität zu synchronisieren. Sie benötigen die synchronisierten Benutzerkonten in Azure AD, um die Lizenzzuweisung und Gruppenverwaltung durchzuführen, um Berechtigungen zu konfigurieren und um andere Verwaltungsaufgaben auszuführen, die Benutzerkonten umfassen.

### <a name="administration"></a>Verwaltung

Da die ursprünglichen und autorisierenden Benutzerkonten im lokalen AD DS gespeichert sind, verwalten Sie Ihre Identitäten mit denselben Tools wie Ihre AD DS.

Sie verwenden nicht die Microsoft 365 Admin Center oder PowerShell für Microsoft 365, um synchronisierte Benutzerkonten in Azure AD zu verwalten.

## <a name="next-step"></a>Nächster Schritt

Wenn Sie das reine Cloudidentitätsmodell benötigen, lesen Sie ["Reine Cloudidentität".](cloud-only-identities.md)

Wenn Sie das Hybrididentitätsmodell benötigen, finden Sie weitere Informationen unter ["Hybrididentität".](plan-for-directory-synchronization.md)

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
