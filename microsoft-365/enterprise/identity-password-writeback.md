---
title: 'Schritt 9: Vereinfachen der Kennwortaktualisierungen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und konfigurieren Sie das Kennwortrückschreiben für Hybridumgebungen.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867741"
---
# <a name="step-9-simplify-password-updates"></a>Schritt 9: Vereinfachen der Kennwortaktualisierungen

*Dieser Schritt ist optional für Hybridumgebungen und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt erlauben Sie Benutzern, ihre Kennwörter über Azure Active Directory (AD) zurückzusetzen, das dann zu Ihrem lokalen Windows Server Active Directory (AD) repliziert wird. Dieser Prozess ist als Kennwortrückschreiben bekannt. Dank dem Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über das lokale Windows Server AD aktualisieren, wo Benutzerkonten und ihre Attribute gespeichert sind. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.

Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn ein hohes Risiko einer Kontogefährdung besteht.

Weitere Informationen und Hinweise zur Konfiguration finden Sie unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).

>[!Note]
>Führen Sie ein Upgrade auf die neueste Version von Azure AD Connect durch, um das bestmögliche Benutzererlebnis und die Verfügbarkeit neuer Features sicherzustellen, sobald diese veröffentlicht werden. Weitere Informationen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).
>

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-pw-writeback) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Vereinfachen der Benutzeranmeldung](identity-single-sign-on.md) |

