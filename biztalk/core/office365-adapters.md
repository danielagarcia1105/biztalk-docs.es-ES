---
title: Usar el adaptador de correo electrónico de Office 365 Outlook | Microsoft Docs
description: Información general de enviar y recibir mensajes mediante los adaptadores de Office 365 Outlook en BizTalk Server, incluido el correo electrónico, calendario y contactos
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946235"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a><span data-ttu-id="f3213-103">Adaptadores de Outlook de Office 365 en BizTalk</span><span class="sxs-lookup"><span data-stu-id="f3213-103">Office 365 Outlook adapters in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="f3213-104">Información general</span><span class="sxs-lookup"><span data-stu-id="f3213-104">Overview</span></span>
<span data-ttu-id="f3213-105">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] característica Pack 3**, puede enviar y recibir mensajes entre las características de BizTalk Server y Office 365 Outlook.</span><span class="sxs-lookup"><span data-stu-id="f3213-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 3**, you can send and receive messages between BizTalk Server and Office 365 Outlook features.</span></span> <span data-ttu-id="f3213-106">Los siguientes adaptadores se incluyen en la característica módulo 3:</span><span class="sxs-lookup"><span data-stu-id="f3213-106">The following adapters are included in Feature Pack 3:</span></span>

- [<span data-ttu-id="f3213-107">Adaptador de correo electrónico de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-107">Office 365 Outlook Email adapter</span></span>](office365-mail-adapter.md)
- [<span data-ttu-id="f3213-108">Adaptador de calendario de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-108">Office 365 Outlook Calendar adapter</span></span>](office365-calendar-adapter.md)
- [<span data-ttu-id="f3213-109">Adaptador de contacto de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-109">Office 365 Outlook Contact adapter</span></span>](office365-contact-adapter.md)

## <a name="prerequisites"></a><span data-ttu-id="f3213-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f3213-110">Prerequisites</span></span>

* <span data-ttu-id="f3213-111">Tiene un [cuenta de Office 365](https://outlook.office365.com)</span><span class="sxs-lookup"><span data-stu-id="f3213-111">Have an [Office 365 account](https://outlook.office365.com)</span></span>
* <span data-ttu-id="f3213-112">Instalar [Feature Pack 3 de](https://aka.ms/bts2016fp3) en el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f3213-112">Install [Feature Pack 3](https://aka.ms/bts2016fp3) on your BizTalk Server</span></span>
* <span data-ttu-id="f3213-113">Usar una cuenta que sea miembro del grupo de administradores de SSO</span><span class="sxs-lookup"><span data-stu-id="f3213-113">Use an account that is a member of the SSO Administrators group</span></span>

## <a name="tms-overview"></a><span data-ttu-id="f3213-114">Información general TMS</span><span class="sxs-lookup"><span data-stu-id="f3213-114">TMS overview</span></span>

<span data-ttu-id="f3213-115">BizTalk Server TMS es un servicio que actualiza los tokens de OAuth de Office 365 usados por BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f3213-115">BizTalk Server TMS is a service that refreshes the Office 365 OAuth tokens used by BizTalk.</span></span> <span data-ttu-id="f3213-116">Actualizan estos tokens periódicamente, lo que garantiza que los tokens siempre sigue siendo válidos.</span><span class="sxs-lookup"><span data-stu-id="f3213-116">It refreshes these tokens periodically, ensuring that the tokens always remain valid.</span></span> <span data-ttu-id="f3213-117">Tiene una dependencia en el servicio Enterprise Single Sign On (SSO ENT) y debe instalarse en un equipo que hospeda el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="f3213-117">It has a dependency on Enterprise Single Sign On service (ENT SSO), and must be installed on a computer that hosts the master secret server.</span></span> 

## <a name="install-biztalk-server-tms"></a><span data-ttu-id="f3213-118">Instalar a BizTalk Server TMS</span><span class="sxs-lookup"><span data-stu-id="f3213-118">Install BizTalk Server TMS</span></span>

1. <span data-ttu-id="f3213-119">Instalar [Feature Pack 3 de](https://aka.ms/bts2016fp3).</span><span class="sxs-lookup"><span data-stu-id="f3213-119">Install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>
2. <span data-ttu-id="f3213-120">En `\Program Files (x86)\Microsoft BizTalk Server <your version>`, ejecute BizTalkTMS.msi.</span><span class="sxs-lookup"><span data-stu-id="f3213-120">In `\Program Files (x86)\Microsoft BizTalk Server <your version>`, run BizTalkTMS.msi.</span></span>
3. <span data-ttu-id="f3213-121">Escriba el nombre de usuario y la contraseña de un usuario que sea miembro del grupo de administradores de SSO.</span><span class="sxs-lookup"><span data-stu-id="f3213-121">Enter the username and password of a user that's a member of the SSO Administrators group.</span></span> 

![Programa de instalación de BizTalk Server TMS](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a><span data-ttu-id="f3213-123">Inicie sesión en Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-123">Sign-in to Office 365</span></span>

<span data-ttu-id="f3213-124">Cuando creas un [puerto de envío](how-to-create-a-send-port2.md) o [ubicación de recepción](how-to-create-a-receive-location.md) en administración de BizTalk, puede **inicio de sesión...**  a su cuenta de Office 365:</span><span class="sxs-lookup"><span data-stu-id="f3213-124">When you're creating a [send port](how-to-create-a-send-port2.md) or [receive location](how-to-create-a-receive-location.md) in BizTalk Administration, you can **Sign-in...** to your Office 365 account:</span></span>

  ![Inicio de sesión de Office 365](../core/media/office365-signin.png)

<span data-ttu-id="f3213-126">Escriba las credenciales de Office 365 y confirmar los permisos.</span><span class="sxs-lookup"><span data-stu-id="f3213-126">You enter the Office 365 credentials, and confirm permissions.</span></span> <span data-ttu-id="f3213-127">Estas credenciales autorización BizTalk al que conectarse y acceder a la cuenta de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3213-127">These credentials authorize BizTalk to connect to, and access the Office 365 account.</span></span> <span data-ttu-id="f3213-128">En el ejemplo siguiente, puede ver los permisos para el calendario de Outlook de Office 365:</span><span class="sxs-lookup"><span data-stu-id="f3213-128">In the following example, you see the permissions for Office 365 Outlook Calendar:</span></span>

  ![Permisos del calendario de Office 365](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a><span data-ttu-id="f3213-130">Introducción</span><span class="sxs-lookup"><span data-stu-id="f3213-130">Get started</span></span>
<span data-ttu-id="f3213-131">Después de instalar BizTalk Server TMS, está listo para crear los artefactos y empezar a usar los adaptadores:</span><span class="sxs-lookup"><span data-stu-id="f3213-131">After BizTalk Server TMS is installed, you're ready to create the artifacts, and start using the adapters:</span></span>

- [<span data-ttu-id="f3213-132">Adaptador de correo electrónico de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-132">Office 365 Outlook Email adapter</span></span>](./office365-mail-adapter.md)
- [<span data-ttu-id="f3213-133">Adaptador de calendario de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-133">Office 365 Outlook Calendar adapter</span></span>](./office365-calendar-adapter.md)
- [<span data-ttu-id="f3213-134">Adaptador de contacto de Outlook de Office 365</span><span class="sxs-lookup"><span data-stu-id="f3213-134">Office 365 Outlook Contact adapter</span></span>](./office365-contact-adapter.md)
