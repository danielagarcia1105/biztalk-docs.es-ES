---
title: Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-a-computer-running-biztalk-server"></a><span data-ttu-id="4d704-102">Realizar una copia de seguridad de un equipo en el que se ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4d704-102">Backing Up a Computer Running BizTalk Server</span></span>
<span data-ttu-id="4d704-103">Si se produce un error de hardware irrecuperable en un equipo en el que se ejecuta BizTalk Server, será preciso sustituirlo con un equipo idéntico.</span><span class="sxs-lookup"><span data-stu-id="4d704-103">If a computer running BizTalk Server suffers an irrecoverable hardware failure, then you must replace that computer with an identical one.</span></span> <span data-ttu-id="4d704-104">Se tendrá que configurar el equipo de sustitución con el software de plataforma base, los requisitos previos de software, los componentes de BizTalk Server y los valores de configuración idénticos.</span><span class="sxs-lookup"><span data-stu-id="4d704-104">You should set up the replacement computer with the base platform software, software prerequisites, BizTalk Server components, and identical configuration settings.</span></span> <span data-ttu-id="4d704-105">Estos valores de configuración pueden componerse de las entradas del Registro, los archivos y las carpetas adecuadas, sí como los servicios de Windows necesarios para que las aplicaciones de BizTalk funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d704-105">These configuration settings may consist of the appropriate registry entries, files, folders, and related Windows services necessary for the correct operation of your BizTalk applications.</span></span>  
  
 <span data-ttu-id="4d704-106">Además de realizar una copia de seguridad de las bases de datos de BizTalk Server, se tendrá que realizar una copia de seguridad de los siguientes componentes de BizTalk Server para garantizar la posibilidad de recuperación de BizTalk Server tras un error de hardware:</span><span class="sxs-lookup"><span data-stu-id="4d704-106">In addition to backing up the BizTalk Server databases, you should back up the following BizTalk Server components to ensure that you can recover BizTalk Server after a hardware failure:</span></span>  
  
-   <span data-ttu-id="4d704-107">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4d704-107">BizTalk Server configuration</span></span>  
  
-   <span data-ttu-id="4d704-108">Secreto principal de inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="4d704-108">Enterprise Single Sign-On (SSO) master secret</span></span>  
  
-   <span data-ttu-id="4d704-109">Portal de Supervisión de la actividad económica (SAE) (no requerido a menos que se utilice SAE)</span><span class="sxs-lookup"><span data-stu-id="4d704-109">Business Activity Monitoring (BAM) portal (not required unless you're using BAM)</span></span>  
  
-   <span data-ttu-id="4d704-110">Aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4d704-110">BizTalk applications</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d704-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d704-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4d704-112">Cómo hacer copia de seguridad de la configuración de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4d704-112">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [<span data-ttu-id="4d704-113">Cómo realizar copias de seguridad del secreto principal</span><span class="sxs-lookup"><span data-stu-id="4d704-113">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="4d704-114">Cómo realizar copias de seguridad del Portal de BAM</span><span class="sxs-lookup"><span data-stu-id="4d704-114">How to Back Up the BAM Portal</span></span>](../core/how-to-back-up-the-bam-portal.md)  
  
-   [<span data-ttu-id="4d704-115">Copia de seguridad de aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4d704-115">Backing Up BizTalk Server Applications</span></span>](../core/backing-up-biztalk-server-applications.md)