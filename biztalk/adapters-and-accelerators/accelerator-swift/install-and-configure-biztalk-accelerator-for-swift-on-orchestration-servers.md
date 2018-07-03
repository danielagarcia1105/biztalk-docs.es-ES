---
title: Instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6811d3dd79de75968b3976b7568075158017609d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985086"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a><span data-ttu-id="78bfb-102">Instalar y configurar el Acelerador de BizTalk para SWIFT en los servidores de orquestación</span><span class="sxs-lookup"><span data-stu-id="78bfb-102">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>
<span data-ttu-id="78bfb-103">Esta sección describe cómo instalar y configurar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] en los servidores de orquestación.</span><span class="sxs-lookup"><span data-stu-id="78bfb-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the orchestration servers.</span></span> <span data-ttu-id="78bfb-104">Estos servidores se utilizan principalmente para ejecutar la orquestación de conciliación y reparación de FIN y la orquestación de envío de reparación/nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="78bfb-104">These servers are mainly used to run the FIN Repair and Reconciliation orchestration and the Message Repair/New Submission orchestration.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a><span data-ttu-id="78bfb-105">Para instalar y configurar el Acelerador de BizTalk para SWIFT en el servidor de orquestación</span><span class="sxs-lookup"><span data-stu-id="78bfb-105">To install and configure BizTalk Accelerator for SWIFT on the orchestration server</span></span>  

1. <span data-ttu-id="78bfb-106">Realizar una instalación personalizada de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78bfb-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="78bfb-107">Instalar el **MRSR** característica.</span><span class="sxs-lookup"><span data-stu-id="78bfb-107">Install the **MRSR** feature.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="78bfb-108">No es necesario instalar los componentes Web para la característica de reparación de mensajes y nuevo envío porque este servidor no tiene el sitio MRSR.</span><span class="sxs-lookup"><span data-stu-id="78bfb-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="78bfb-109">Una vez completada la instalación, se inicia el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="78bfb-109">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="78bfb-110">En Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] configuración de la consola, configure **MCRR**.</span><span class="sxs-lookup"><span data-stu-id="78bfb-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>
