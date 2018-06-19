---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for SWIFT, configuring
- BizTalk Accelerator for SWIFT, installing on Messaging servers
- BizTalk Messaging servers, installing BizTalk Accelerator for SWIFT
ms.assetid: 7a8f60aa-5ff2-4584-9d4a-dc4a0ba61aca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef434603c1740375f4399f368e89f99a923cba86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209396"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-messaging-servers"></a><span data-ttu-id="45e48-102">Instalar y configurar el Acelerador de BizTalk para SWIFT en servidores de mensajería</span><span class="sxs-lookup"><span data-stu-id="45e48-102">Installing and Configuring BizTalk Accelerator for SWIFT on Messaging Servers</span></span>
<span data-ttu-id="45e48-103">Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores de mensajería.</span><span class="sxs-lookup"><span data-stu-id="45e48-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the messaging servers.</span></span> <span data-ttu-id="45e48-104">Estos servidores se utilizan principalmente para comunicarse con la red SWIFT.</span><span class="sxs-lookup"><span data-stu-id="45e48-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-a4swift-on-the-messaging-server"></a><span data-ttu-id="45e48-105">Para instalar y configurar el Acelerador de BizTalk para A4SWIFT en el servidor de mensajería</span><span class="sxs-lookup"><span data-stu-id="45e48-105">To install and configure BizTalk Accelerator for A4SWIFT on the Messaging Server</span></span>  
  
1.  <span data-ttu-id="45e48-106">Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45e48-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="45e48-107">Instalar el **MRSR** y **mensajes de SWIFT** características.</span><span class="sxs-lookup"><span data-stu-id="45e48-107">Install the **MRSR** and **SWIFT Messages** features.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45e48-108">No es necesario instalar los componentes Web para la característica de reparación de mensajes y nuevo envío porque este servidor no tiene sitios MRSR.</span><span class="sxs-lookup"><span data-stu-id="45e48-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45e48-109">Una vez completada la instalación, se inicia el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="45e48-109">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="45e48-110">En el Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR**.</span><span class="sxs-lookup"><span data-stu-id="45e48-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>