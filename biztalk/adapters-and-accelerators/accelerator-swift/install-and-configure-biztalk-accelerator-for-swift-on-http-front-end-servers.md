---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 375f5f26c9c71554f4ad44bd688f1d715cb81b92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973461"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="de72c-102">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="de72c-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="de72c-103">Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores front-end HTTP.</span><span class="sxs-lookup"><span data-stu-id="de72c-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="de72c-104">Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="de72c-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="de72c-105">Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="de72c-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  

1. <span data-ttu-id="de72c-106">Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de72c-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="de72c-107">Instalar el **MRSR** y **componentes Web de reparación de mensajes y nuevo envío** características.</span><span class="sxs-lookup"><span data-stu-id="de72c-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de72c-108">Una vez completada la instalación, se inicia el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="de72c-108">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="de72c-109">En Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR** y **WebService**.</span><span class="sxs-lookup"><span data-stu-id="de72c-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  

3. <span data-ttu-id="de72c-110">Después de completar el Asistente de configuración en los servidores Web, abra el archivo web.config en la carpeta \< *unidad*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="de72c-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="de72c-111">Búsqueda de "Autorización".</span><span class="sxs-lookup"><span data-stu-id="de72c-111">Search for "Authorization".</span></span> <span data-ttu-id="de72c-112">En el **autorización** sección, establezca el valor de roles en el nombre del grupo de usuarios de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="de72c-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>
