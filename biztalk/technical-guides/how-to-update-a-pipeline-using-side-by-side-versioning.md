---
title: Cómo actualizar una canalización mediante el control de versiones en paralelo | Documentos de Microsoft
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
ms.openlocfilehash: 8a5b977d8f0d1964df33c2b2f549bd420d0d3179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008381"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="559b4-102">Cómo actualizar una canalización mediante el control de versiones en paralelo</span><span class="sxs-lookup"><span data-stu-id="559b4-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="559b4-103">El método sencillo para usar una nueva canalización agregada por el control de versiones en paralelo consiste en seleccionar la versión de canalización recién implementado en el puerto de envío o ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="559b4-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="559b4-104">Esto reemplazará la canalización antigua con uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="559b4-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="559b4-105">Sin embargo, si necesita verdadera funcionalidad en paralelo para la compatibilidad con versiones anteriores, a continuación, debe crear nuevos puertos de envío y ubicaciones de recepción y enlazarlos a la nueva versión de canalización especificada.</span><span class="sxs-lookup"><span data-stu-id="559b4-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="559b4-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="559b4-106">Prerequisites</span></span>  
 <span data-ttu-id="559b4-107">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="559b4-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="559b4-108">Para agregar una nueva versión de un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="559b4-108">To add a new version of a pipeline component</span></span>  
  
1.  <span data-ttu-id="559b4-109">En Visual Studio, cree una nueva versión del componente de canalización y firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="559b4-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2.  <span data-ttu-id="559b4-110">Agregue el componente de canalización en el **componentes de canalización** carpeta (\<*carpeta de instalación*\>\Pipeline componentes).</span><span class="sxs-lookup"><span data-stu-id="559b4-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3.  <span data-ttu-id="559b4-111">Agregue el componente de canalización a la canalización.</span><span class="sxs-lookup"><span data-stu-id="559b4-111">Add the pipeline component to your pipeline.</span></span>  
  
4.  <span data-ttu-id="559b4-112">Después de compilar la canalización o implementar la solución, quite el componente de canalización de la **componentes de canalización** carpeta.</span><span class="sxs-lookup"><span data-stu-id="559b4-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5.  <span data-ttu-id="559b4-113">Agregue el componente de canalización a la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="559b4-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="559b4-114">Después de completar estos pasos, el ensamblado de canalización compilado hará referencia a la versión correcta del componente de canalización y AppDomain utilizado por BizTalk Server encontrará la nueva versión del componente de canalización en la GAC, en lugar de Buscar anterior versión del componente de canalización en la carpeta de componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="559b4-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="559b4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="559b4-115">See Also</span></span>  
 [<span data-ttu-id="559b4-116">Actualización mediante el control de versiones en paralelo</span><span class="sxs-lookup"><span data-stu-id="559b4-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)