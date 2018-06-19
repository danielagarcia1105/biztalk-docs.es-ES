---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP | Documentos de Microsoft
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
ms.openlocfilehash: f8a63277ec58981f5f0f904aabe61957de66df08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965674"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="5e253-102">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="5e253-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="5e253-103">Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores front-end de HTTP.</span><span class="sxs-lookup"><span data-stu-id="5e253-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="5e253-104">Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5e253-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="5e253-105">Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor front-end HTTP</span><span class="sxs-lookup"><span data-stu-id="5e253-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  
  
1.  <span data-ttu-id="5e253-106">Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e253-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="5e253-107">Instalar el **MRSR** y **componentes Web de reparación de mensajes y nuevo envío** características.</span><span class="sxs-lookup"><span data-stu-id="5e253-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e253-108">Una vez completada la instalación, se inicia el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="5e253-108">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="5e253-109">En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR** y **WebService**.</span><span class="sxs-lookup"><span data-stu-id="5e253-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  
  
3.  <span data-ttu-id="5e253-110">Después de completar el Asistente para configuración, en los servidores Web, abra el archivo web.config en la carpeta \< *unidad*\>: \Program [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="5e253-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="5e253-111">Búsqueda de "Autorización".</span><span class="sxs-lookup"><span data-stu-id="5e253-111">Search for "Authorization".</span></span> <span data-ttu-id="5e253-112">En el **autorización** sección, establezca el valor de roles en el nombre del grupo de usuarios de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="5e253-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>