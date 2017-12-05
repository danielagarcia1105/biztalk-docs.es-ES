---
title: "Implementar componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041bd8c6e6fa9c3969be18f0804460c00de5f11a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-pipeline-components"></a><span data-ttu-id="957b3-102">Implementar componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="957b3-102">Deploying Pipeline Components</span></span>
<span data-ttu-id="957b3-103">Todas la canalización componente ensamblados .NET (nativos y personalizados) deben estar ubicados en el \< *directorio de instalación de*\>carpeta \Pipeline Components para ser ejecutado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="957b3-103">All the .NET pipeline component assemblies (native and custom) must be located in the \<*installation directory*\>\Pipeline Components folder to be executed by the server.</span></span> <span data-ttu-id="957b3-104">Si la canalización que tiene un componente personalizado se va a implementar en varios servidores, los archivos binarios del componente deben estar presentes en la carpeta especificada de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="957b3-104">If the pipeline with a custom component will be deployed across several servers, the component's binaries must be present in the specified folder on every server.</span></span>  
  
 <span data-ttu-id="957b3-105">No es necesario que agregue un componente de canalización personalizado para que lo use el Tiempo de ejecución de BizTalk en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="957b3-105">You do not need to add a custom pipeline component to be used by the BizTalk Runtime to the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="957b3-106">Los componentes COM personalizados de la canalización aparecerán en el Cuadro de herramientas, siempre y cuando se registren en el equipo como un componente COM.</span><span class="sxs-lookup"><span data-stu-id="957b3-106">Custom COM components in the pipeline will also appear in the Toolbox, provided they are registered on the computer as a COM component.</span></span> <span data-ttu-id="957b3-107">Componentes de canalización de .NET personalizados se deben colocar en el \< *directorio de instalación de*\>carpeta \Pipeline Components.</span><span class="sxs-lookup"><span data-stu-id="957b3-107">Custom .NET pipeline components must be placed into the \<*installation directory*\>\Pipeline Components folder.</span></span>  
  
 <span data-ttu-id="957b3-108">Una vez que los archivos binarios están en la ubicación correcta, es necesario que agregue el componente al Cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="957b3-108">After the binary files are in the correct location, you need to add the component to the Toolbox.</span></span> <span data-ttu-id="957b3-109">Para obtener instrucciones sobre cómo agregar el componente de canalización al cuadro de herramientas, consulte [cómo utilizar el cuadro de herramientas](../core/how-to-use-the-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="957b3-109">For instructions on adding the pipeline component to the Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957b3-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="957b3-110">See Also</span></span>  
 [<span data-ttu-id="957b3-111">Desarrollo de componentes de canalización personalizados</span><span class="sxs-lookup"><span data-stu-id="957b3-111">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)