---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe0a320f9f60f72975faf903c1355b8730840b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="a6ce1-102">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="a6ce1-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="a6ce1-103">Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores front-end de HTTP.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="a6ce1-104">Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="a6ce1-105">Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="a6ce1-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  
  
1.  <span data-ttu-id="a6ce1-106">Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ce1-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="a6ce1-107">Instalar el **MRSR** y **componentes Web de reparación de mensajes y nuevo envío** características.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a6ce1-108">Una vez completada la instalación, se inicia el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-108">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="a6ce1-109">En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR** y **WebService**.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  
  
3.  <span data-ttu-id="a6ce1-110">Después de completar el Asistente para configuración, en los servidores Web, abra el archivo web.config en la carpeta \< *unidad*>: \Program [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="a6ce1-111">Búsqueda de "Autorización".</span><span class="sxs-lookup"><span data-stu-id="a6ce1-111">Search for "Authorization".</span></span> <span data-ttu-id="a6ce1-112">En el **autorización** sección, establezca el valor de roles en el nombre del grupo de usuarios de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="a6ce1-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>