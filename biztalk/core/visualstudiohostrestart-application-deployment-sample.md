---
title: "VisualStudioHostRestart (ejemplo de implementación de aplicaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74289ae59ef96c579b3c132fd76f1d0e8e77cf13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a><span data-ttu-id="d2184-102">VisualStudioHostRestart (ejemplo de implementación de aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="d2184-102">VisualStudioHostRestart (Application Deployment Sample)</span></span>
<span data-ttu-id="d2184-103">En este tema se explica como utilizar la secuencia de comandos de ejemplo VisualStudioHostRestart para reiniciar una instancia de host que se ejecuta en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="d2184-103">This topic explains how to use the VisualStudioHostRestart sample script to restart a host instance running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="d2184-104">Puede utilizar esta secuencia de comandos a la hora de volver a implementar ensamblados en Visual Studio, de manera que el tiempo de ejecución de BizTalk Server adopta los cambios de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="d2184-104">You can use this script when redeploying assemblies in Visual Studio so that the BizTalk Server runtime immediately picks up the changes.</span></span> <span data-ttu-id="d2184-105">Como alternativa, puede usar la opción para reiniciar instancias de host que puede establecer en las propiedades de implementación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d2184-105">Alternatively, you can use the option to restart host instances, which you can set in Deployment properties for the project.</span></span> <span data-ttu-id="d2184-106">Para obtener más información, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d2184-106">For more information, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d2184-107">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2184-107">What This Sample Does</span></span>  
 <span data-ttu-id="d2184-108">Esta secuencia de comandos de ejemplo lleva a cabo las siguientes acciones en este orden:</span><span class="sxs-lookup"><span data-stu-id="d2184-108">This sample script performs the following actions, in order:</span></span>  
  
1.  <span data-ttu-id="d2184-109">Detener todas las instancias de host en curso en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d2184-109">Stops all in-process host instances on the local computer.</span></span>  
  
2.  <span data-ttu-id="d2184-110">Iniciar todas las instancias de host en curso en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="d2184-110">Starts all in-process host instances on the local computer.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d2184-111">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2184-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="d2184-112">El ejemplo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] carpeta de instalación, como se indica a continuación:  *\<ruta de ejemplos >*\Application Deployment\VisualStudioHostRestart.</span><span class="sxs-lookup"><span data-stu-id="d2184-112">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows: *\<Samples path>*\Application Deployment\VisualStudioHostRestart.</span></span>  
  
 <span data-ttu-id="d2184-113">En el ejemplo se incluye el archivo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d2184-113">The sample includes the following file:</span></span>  
  
-   <span data-ttu-id="d2184-114">RestartBizTalkHostInstances.vbs</span><span class="sxs-lookup"><span data-stu-id="d2184-114">RestartBizTalkHostInstances.vbs</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="d2184-115">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2184-115">How to Use This Sample</span></span>  
 <span data-ttu-id="d2184-116">Utilice los procedimientos que se exponen a continuación para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d2184-116">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="d2184-117">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2184-117">To run the sample</span></span>  
  
-   <span data-ttu-id="d2184-118">Ejecute el archivo RestartBizTalkHostInstances.vbs.</span><span class="sxs-lookup"><span data-stu-id="d2184-118">Run RestartBizTalkHostInstances.vbs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2184-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2184-119">See Also</span></span>  
 <span data-ttu-id="d2184-120">[Implementación de aplicaciones (carpeta de ejemplos de BizTalk Server)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="d2184-120">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 <span data-ttu-id="d2184-121">[Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="d2184-121">[Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="d2184-122">Implementar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d2184-122">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)