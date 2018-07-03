---
title: Cómo actualizar una canalización mediante el control de versiones en paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf978b64876a91d06acfbe4c5d34278935cfa55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970893"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="e7d15-102">Cómo actualizar una canalización mediante el control de versiones en paralelo</span><span class="sxs-lookup"><span data-stu-id="e7d15-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="e7d15-103">Es una manera sencilla de usar una nueva canalización agregada por el control de versiones en paralelo seleccionar la versión de canalización recién implementado en el puerto de envío o ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e7d15-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="e7d15-104">Esto reemplazará la canalización antigua con uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="e7d15-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="e7d15-105">Sin embargo, si necesita verdadera funcionalidad en paralelo para la compatibilidad con versiones anteriores, a continuación, debe crear nuevos puertos de envío y ubicaciones de recepción y enlazarlos a la nueva versión de canalización especificada.</span><span class="sxs-lookup"><span data-stu-id="e7d15-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e7d15-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e7d15-106">Prerequisites</span></span>  
 <span data-ttu-id="e7d15-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e7d15-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="e7d15-108">Para agregar una nueva versión de un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="e7d15-108">To add a new version of a pipeline component</span></span>  
  
1. <span data-ttu-id="e7d15-109">En Visual Studio, cree una nueva versión del componente de canalización y firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7d15-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2. <span data-ttu-id="e7d15-110">Agregar el componente de canalización en el **componentes de canalización** carpeta (\<*carpeta de instalación*\>\Pipeline Components).</span><span class="sxs-lookup"><span data-stu-id="e7d15-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3. <span data-ttu-id="e7d15-111">Agregue el componente de canalización a la canalización.</span><span class="sxs-lookup"><span data-stu-id="e7d15-111">Add the pipeline component to your pipeline.</span></span>  
  
4. <span data-ttu-id="e7d15-112">Después de crear la canalización o implementar la solución, quite el componente de canalización desde el **componentes de canalización** carpeta.</span><span class="sxs-lookup"><span data-stu-id="e7d15-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5. <span data-ttu-id="e7d15-113">Agregue el componente de canalización a la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="e7d15-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
   <span data-ttu-id="e7d15-114">Después de haber completado estos pasos, hará referencia al ensamblado de canalización compilado a la versión correcta del componente de canalización y el dominio de aplicación que utiliza BizTalk Server encontrará la nueva versión del componente de canalización en la GAC, en lugar de Buscar anterior versión del componente de canalización en la carpeta de componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="e7d15-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d15-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7d15-115">See Also</span></span>  
 [<span data-ttu-id="e7d15-116">Actualización mediante el control de versiones en paralelo</span><span class="sxs-lookup"><span data-stu-id="e7d15-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)