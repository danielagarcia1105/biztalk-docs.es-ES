---
title: Ejecutar el ejemplo de servicio de control de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d69e720c-89e4-42c2-b4d0-31f0b865ab7f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabab8678d8ee8b65854e494ce0a2ec53eba78fb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999397"
---
# <a name="running-the-exception-handling-service-sample"></a><span data-ttu-id="51661-102">Ejecutar el ejemplo de servicio de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="51661-102">Running the Exception Handling Service Sample</span></span>
<span data-ttu-id="51661-103">El ejemplo de servicio de control de excepciones muestra cómo consumir el servicio Web de control de excepciones para enviar un error en el marco de control de excepciones de ESB desde una aplicación externa.</span><span class="sxs-lookup"><span data-stu-id="51661-103">The Exception Handling Service sample demonstrates how to consume the Exception Handling Web Service in order to submit a fault into the ESB Exception Handling Framework from an external application.</span></span> <span data-ttu-id="51661-104">El procedimiento siguiente para ejecutar este ejemplo requiere [instalar los ejemplos de administración de excepciones](../esb-toolkit/installing-the-exception-management-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51661-104">The following procedure for running this sample requires [Installing the Exception Management Samples](../esb-toolkit/installing-the-exception-management-samples.md).</span></span>  
  
 <span data-ttu-id="51661-105">**Para ejecutar el ejemplo de servicio de control de excepciones**</span><span class="sxs-lookup"><span data-stu-id="51661-105">**To run the Exception Handling Service sample**</span></span>  
  
1. <span data-ttu-id="51661-106">En el Explorador de Windows, abra la carpeta \Source\Samples\ExceptionHandlingService, donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos y, a continuación, abra el archivo de solución de Visual Studio denominado ExceptionHandlingService.sln.</span><span class="sxs-lookup"><span data-stu-id="51661-106">In Windows Explorer, open the folder \Source\Samples\ExceptionHandlingService, where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then open the Visual Studio solution file named ExceptionHandlingService.sln.</span></span>  
  
2. <span data-ttu-id="51661-107">En Visual Studio, haga clic en **Iniciar depuración** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="51661-107">In Visual Studio, click **Start Debugging** on the Toolbar.</span></span>  
  
3. <span data-ttu-id="51661-108">En el formulario que se carga, haga clic en el **generar excepciones** botón.</span><span class="sxs-lookup"><span data-stu-id="51661-108">On the form that loads, click the **Generate Exception** button.</span></span>  
  
4. <span data-ttu-id="51661-109">En el Explorador de Windows, abra la carpeta de \Samples\Exception Handling\Test\Filedrop\All_Exceptions y, a continuación, abra el archivo .xml de Exceptions_ {GUID} más reciente.</span><span class="sxs-lookup"><span data-stu-id="51661-109">In Windows Explorer, open the folder \Samples\Exception Handling\Test\Filedrop\All_Exceptions, and then open the most recent Exceptions_{GUID}.xml file.</span></span>  
  
5. <span data-ttu-id="51661-110">Examine el contenido de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="51661-110">Examine the contents of the generated exception.</span></span>  
  
   <span data-ttu-id="51661-111">Para obtener más información acerca de cómo el ejemplo de servicio de control de excepciones usa el servicio de administración de excepciones, vea [excepción control servicio ejemplo funcionamiento](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span><span class="sxs-lookup"><span data-stu-id="51661-111">For more information about how the Exception Handling Service sample uses the Exception Management service, see [How the Exception Handling Service Sample Works](../esb-toolkit/how-the-exception-handling-service-sample-works.md).</span></span>