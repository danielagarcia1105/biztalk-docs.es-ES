---
title: Configurar el adaptador WCF para interceptar datos BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd705c27-5d04-47e5-9bb2-61235f8fe544
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f418512ecd0a3e38f884965d1698579fb300dd74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-wcf-adapter-to-intercept-bam-data"></a><span data-ttu-id="9afe3-102">Configurar el adaptador de WCF para interceptar datos de BAM</span><span class="sxs-lookup"><span data-stu-id="9afe3-102">Configuring the WCF Adapter to Intercept BAM Data</span></span>
<span data-ttu-id="9afe3-103">Esta sección contiene información acerca de los pasos que se deben seguir para configurar el adaptador de WCF de BizTalk para que funcione con el interceptor de WCF de BAM.</span><span class="sxs-lookup"><span data-stu-id="9afe3-103">This section contains information about the steps you must take to configure the BizTalk WCF adapter to work with the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="9afe3-104">Los pasos básicos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9afe3-104">The basic steps are as follows:</span></span>  
  
-   <span data-ttu-id="9afe3-105">Agregar el comportamiento de BAM al archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9afe3-105">Add the BAM behavior to the machine.config file.</span></span>  
  
-   <span data-ttu-id="9afe3-106">Crear un adaptador de WCF de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9afe3-106">Create a BizTalk WCF adapter.</span></span>  
  
-   <span data-ttu-id="9afe3-107">Configurar la intercepción de WCF de BAM.</span><span class="sxs-lookup"><span data-stu-id="9afe3-107">Configure the BAM WCF interception.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9afe3-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9afe3-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9afe3-109">Cómo agregar el comportamiento del Interceptor BAM al archivo Machine.config</span><span class="sxs-lookup"><span data-stu-id="9afe3-109">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)  
  
-   [<span data-ttu-id="9afe3-110">Cómo crear un adaptador de WCF para BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9afe3-110">How to Create a WCF Adapter for BizTalk Server</span></span>](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)  
  
-   [<span data-ttu-id="9afe3-111">Cómo configurar la recepción y envío ubicaciones y puertos para la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="9afe3-111">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="9afe3-112">Cómo configurar la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="9afe3-112">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="9afe3-113">Use el control de errores</span><span class="sxs-lookup"><span data-stu-id="9afe3-113">Using Fault Handling</span></span>](../core/using-fault-handling.md)