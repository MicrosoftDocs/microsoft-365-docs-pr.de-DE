---
title: Office 365 Skype for Business Datenlöschung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung der Datenlöschung in Skype for Business, einschließlich der Art von Inhalten, die nicht beibehalten werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf317f2ecd3d547ae8601553a34fb43fb4b5bd9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690715"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="cab7e-103">Skype for Business von Datenlöschung in Office 365</span><span class="sxs-lookup"><span data-stu-id="cab7e-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="cab7e-p101">Skype for Business ermöglicht das Archivieren von Peer-zu-Peer-Chatnachrichten, Chatnachrichten mit mehreren Teilnehmern und das Hochladen von Inhalt in Besprechungen. Zum Archivieren ist Exchange erforderlich, und die Funktion wird vom Compliance-Archiv-Attribut für das Exchange-Postfach des Benutzers gesteuert, mit dem sowohl E-Mails als auch Skype for Business-Inhalte archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="cab7e-p101">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings. The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="cab7e-p102">Die gesamte Archivierung in Skype for Business wird als "Archivierung auf Benutzerebene" bezeichnet, da sie für bestimmte Benutzer oder Benutzergruppen aktiviert bzw. deaktiviert wird, indem eine Richtlinie für die Archivierung auf Benutzerebene für diese Benutzer erstellt, konfiguriert und angewendet wird. Das Skype for Business Admin Center bietet keine Möglichkeit zum direkten Steuern von Archivierungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="cab7e-p102">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users. There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="cab7e-108">Die folgenden Inhaltstypen werden in Skype for Business nicht archiviert:</span><span class="sxs-lookup"><span data-stu-id="cab7e-108">The following types of content are not archived in Skype for Business:</span></span>

- <span data-ttu-id="cab7e-109">Peer-zu-Peer-Dateiübertragungen</span><span class="sxs-lookup"><span data-stu-id="cab7e-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="cab7e-110">Audio/Video für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="cab7e-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="cab7e-111">Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -Konferenzen</span><span class="sxs-lookup"><span data-stu-id="cab7e-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="cab7e-112">Anmerkungen zu Konferenzen</span><span class="sxs-lookup"><span data-stu-id="cab7e-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="cab7e-113">Erfüllen der Inhaltsaufbewahrung</span><span class="sxs-lookup"><span data-stu-id="cab7e-113">Meeting Content Retention</span></span>

<span data-ttu-id="cab7e-114">Kunden, die Skype for Business verwenden, können Inhalte in eine Skype for Business Besprechung als Anlagen hochladen, beispielsweise PowerPoint-Präsentationen, OneNote-Dateien und andere Dateien.</span><span class="sxs-lookup"><span data-stu-id="cab7e-114">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files.</span></span> <span data-ttu-id="cab7e-115">Für Inhalte, die in eine Besprechung hochgeladen werden, gilt folgende Aufbewahrungsdauer:</span><span class="sxs-lookup"><span data-stu-id="cab7e-115">The retention period for content that has been uploaded to a meeting is as follows:</span></span>

- <span data-ttu-id="cab7e-116">**Einmaliger Besprechungs** Inhalt wird 15 Tage lang aufbewahrt, beginnend mit dem Zeitpunkt, an dem die letzte Person die Besprechung verlässt.</span><span class="sxs-lookup"><span data-stu-id="cab7e-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="cab7e-117">Besprechungs **Serie** – Inhalte werden 15 Tage lang aufbewahrt, nachdem die letzte Person die letzte Besprechungs Sitzung verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="cab7e-117">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting.</span></span> <span data-ttu-id="cab7e-118">Der Aufbewahrungstimer wird zurückgesetzt, wenn jemand innerhalb von 15 Tagen an dieser Besprechungssitzung teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="cab7e-118">The retention timer resets if someone joins the same meeting session within 15 days.</span></span> <span data-ttu-id="cab7e-119">Nehmen wir beispielsweise an, dass eine Skype for Business Besprechung für ein Jahr auf wöchentlicher Basis stattfindet und eine Datei während der ersten Instanz in die Besprechung hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="cab7e-119">For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance.</span></span> <span data-ttu-id="cab7e-120">Wenn jede Woche mindestens eine Person der Besprechungs Sitzung Beitritt, wird die Datei in Skype for Business Online Servern für das gesamte Jahr aufbewahrt, und zwar 15 Tage nachdem die letzte Person die letzte Besprechung der Datenreihe verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="cab7e-120">If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="cab7e-121">**Sofortbesprechung** – Inhalte werden 8 Stunden nach der Besprechungs Endzeit aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="cab7e-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="cab7e-122">Wenn ein Benutzer nicht lizenziert oder deaktiviert ist (beispielsweise wenn **msRTCSIP-UserEnabled** auf *false*festgelegt ist) und dann erneut lizenziert oder erneut aktiviert wird, werden Besprechungsinhalte nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="cab7e-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="cab7e-123">Ablauf der Besprechung</span><span class="sxs-lookup"><span data-stu-id="cab7e-123">Meeting Expiration</span></span>

<span data-ttu-id="cab7e-124">Benutzer können nach Ende einer bestimmten Besprechung auf diese zugreifen. Dafür gelten die folgenden Ablaufzeiträume:</span><span class="sxs-lookup"><span data-stu-id="cab7e-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>

- <span data-ttu-id="cab7e-125">**Einmaliges Besprechungs** Meeting läuft 14 Tage nach der geplanten Besprechungs Endzeit ab.</span><span class="sxs-lookup"><span data-stu-id="cab7e-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="cab7e-126">**Wiederkehrende Besprechung mit Enddatum** – Besprechung läuft 14 Tage nach der geplanten Endzeit des letzten Besprechungstermins ab.</span><span class="sxs-lookup"><span data-stu-id="cab7e-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="cab7e-127">" **Jetzt einsehen** "-Besprechungs Sitzung läuft nach 8 Stunden ab.</span><span class="sxs-lookup"><span data-stu-id="cab7e-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="cab7e-128">Whiteboard-Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="cab7e-128">Whiteboard Collaboration</span></span>

<span data-ttu-id="cab7e-129">Anmerkungen auf Whiteboards sind für alle Teilnehmer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="cab7e-129">Annotations made on whiteboards will be seen by all participants.</span></span> <span data-ttu-id="cab7e-130">Beim Speichern eines Whiteboards werden das Whiteboard und alle Anmerkungen auf einem Skype for Business Server gespeichert und auf dem Server entsprechend den vom Administrator festgelegten Richtlinien zum Ablauf von Besprechungsinhalten aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="cab7e-130">When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="cab7e-131">Audio-Test Dienst</span><span class="sxs-lookup"><span data-stu-id="cab7e-131">Audio Test Service</span></span>

<span data-ttu-id="cab7e-132">Ein kurzes Sample ihrer Stimme (ca. 5 Sekunden) wird während des Anrufs für den Audio-Test Dienst aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cab7e-132">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call.</span></span> <span data-ttu-id="cab7e-133">Das VoIP-Beispiel wird von Ihnen verwendet, um die Tonqualität Ihres Skype for Business Anrufs basierend auf der Qualität der Aufzeichnung zu überprüfen und/oder zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cab7e-133">The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording.</span></span> <span data-ttu-id="cab7e-134">Wenn der Anruf des Audiotest Diensts beendet wird, wird das VoIP-Beispiel gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cab7e-134">When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="cab7e-135">Beständiger Gruppen Chat</span><span class="sxs-lookup"><span data-stu-id="cab7e-135">Persistent Group Chat</span></span>

<span data-ttu-id="cab7e-136">Im Chat für beständige Gruppen wird der Inhalt von Gruppenchat Unterhaltungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cab7e-136">Persistent Group Chat stores the content of group chat conversations.</span></span> <span data-ttu-id="cab7e-137">Wenn diese Option aktiviert ist, kann der Administrator den Aufbewahrungszeitraum, den Server, auf dem diese Informationen gespeichert sind, verwalten, wenn der Gruppen Chat Verlauf für die Kompatibilität oder andere Zwecke archiviert wird, und die Eigenschaften für einen Chatroom verwalten/ändern.</span><span class="sxs-lookup"><span data-stu-id="cab7e-137">If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room.</span></span> <span data-ttu-id="cab7e-138">Benutzer mit unterschiedlichen Rollen haben wie folgt unterschiedlichen Zugriff auf die beibehaltenen Daten:</span><span class="sxs-lookup"><span data-stu-id="cab7e-138">Users with different roles have different access to the persisted data, as follows:</span></span>

- <span data-ttu-id="cab7e-139">Administratoren können ältere Inhalte (beispielsweise Inhalte, die vor einem bestimmten Datum veröffentlicht wurden) aus einem Chatroom löschen, damit die Größe der Datenbank nicht größer wird.</span><span class="sxs-lookup"><span data-stu-id="cab7e-139">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly.</span></span> <span data-ttu-id="cab7e-140">Oder Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom unangemessen sind (oder als ungeeignet betrachtet werden).</span><span class="sxs-lookup"><span data-stu-id="cab7e-140">Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="cab7e-141">Endbenutzer, einschließlich Nachrichten Autoren, können keine Inhalte aus Chatrooms löschen.</span><span class="sxs-lookup"><span data-stu-id="cab7e-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="cab7e-142">Chatroom-Manager können Räume deaktivieren, aber keine Räume löschen.</span><span class="sxs-lookup"><span data-stu-id="cab7e-142">Chat room managers can disable rooms but cannot delete rooms.</span></span> <span data-ttu-id="cab7e-143">Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cab7e-143">Only administrators can delete a chat room after it is created.</span></span>