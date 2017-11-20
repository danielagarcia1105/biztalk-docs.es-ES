---
title: Instalar el ejemplo de operaciones de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6307f9d9e4ff9907bab22efcde0755dbdfdc228b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="40327-102">Instalar el ejemplo de operaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="40327-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="40327-103">El ejemplo de operaciones de BizTalk de Microsoft requiere el servicio de operaciones de BizTalk ESB instalado y configurado.</span><span class="sxs-lookup"><span data-stu-id="40327-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="40327-104">Servicio de operaciones de BizTalk ESB es uno de los servicios de Web de básicos que pueden ser instalados y configuran con la herramienta de configuración de ESB.</span><span class="sxs-lookup"><span data-stu-id="40327-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="40327-105">Para obtener más información acerca de cómo utilizar la herramienta de configuración de ESB, consulte [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span><span class="sxs-lookup"><span data-stu-id="40327-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="40327-106">La ubicación predeterminada del servicio Web de las operaciones de BizTalk es http://localhost/ESB.BizTalkOperationsService/Operations.asmx; Sin embargo, puede cambiarlo en el archivo de configuración de aplicación si implementa el servicio en una ubicación diferente o un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="40327-106">The default location of the BizTalk Operations Web service is http://localhost/ESB.BizTalkOperationsService/Operations.asmx; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  
  
 <span data-ttu-id="40327-107">Debe instalar el ejemplo de operaciones de BizTalk desde el proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="40327-107">You must install BizTalk Operations sample from the solution project.</span></span>  
  
 <span data-ttu-id="40327-108">**Para instalar el ejemplo de operaciones de BizTalk**</span><span class="sxs-lookup"><span data-stu-id="40327-108">**To install the BizTalk Operations sample**</span></span>  
  
1.  <span data-ttu-id="40327-109">Abra la solución denominada ESB.BizTalkOperations.Test.Client.csproj desde la carpeta \Source\Samples\BizTalkOperations donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos en [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40327-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="40327-110">Use los comandos en el **generar** menú para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="40327-110">Use the commands on the **Build** menu to compile the solution.</span></span>