---
title: Validar una asignación (EDI) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6cfe1394d82f4fedb57aacb40bad27c95de2a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993341"
---
# <a name="validating-a-map-edi"></a><span data-ttu-id="aa611-102">Validar una asignación (EDI)</span><span class="sxs-lookup"><span data-stu-id="aa611-102">Validating a Map (EDI)</span></span>
<span data-ttu-id="aa611-103">Las asignaciones pueden validarse en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="aa611-103">You can validate a map at design time.</span></span> <span data-ttu-id="aa611-104">Para ello, usa las extensiones de herramientas de XML a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="aa611-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="aa611-105">Esta operación genera un archivo que contiene el XSLT subyacente de la asignación y un archivo que contiene objetos de extensión.</span><span class="sxs-lookup"><span data-stu-id="aa611-105">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa611-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aa611-106">Prerequisites</span></span>  
 <span data-ttu-id="aa611-107">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa611-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-map"></a><span data-ttu-id="aa611-108">Para validar una asignación</span><span class="sxs-lookup"><span data-stu-id="aa611-108">To validate a map</span></span>  
  
1. <span data-ttu-id="aa611-109">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa611-109">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="aa611-110">En el proyecto del Explorador de soluciones, incluya la asignación que desea validar, así como sus esquemas de mensaje de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="aa611-110">To the project in Solution Explorer, add the map that you want to validate and its input and output message schemas.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aa611-111">Los esquemas de mensaje se encuentran en la subcarpeta correspondiente de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span><span class="sxs-lookup"><span data-stu-id="aa611-111">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="aa611-112">Para obtener más información acerca de cómo instalar los archivos de esquema, vea [cómo instalar archivos de esquema EDI](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span><span class="sxs-lookup"><span data-stu-id="aa611-112">For more information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="aa611-113">No tiene que generar el proyecto para validar una asignación.</span><span class="sxs-lookup"><span data-stu-id="aa611-113">You do not have to build the project to validate a map.</span></span>  
  
2. <span data-ttu-id="aa611-114">Haga clic en el mapa en el Explorador de soluciones y, a continuación, haga clic en **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="aa611-114">Right-click the map in Solution Explorer, and then click **Validate Map**.</span></span>  
  
3. <span data-ttu-id="aa611-115">Compruebe que existe un mensaje en la ventana Resultados que le indica que la operación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa611-115">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
4. <span data-ttu-id="aa611-116">Tenga en cuenta las advertencias que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ha publicado en el **salida** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa611-116">Note any warnings that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has posted in the **Output** window.</span></span>  
  
5. <span data-ttu-id="aa611-117">En el **salida** ventana, tenga en cuenta el nombre y ruta de acceso de la salida XSLT.</span><span class="sxs-lookup"><span data-stu-id="aa611-117">In the **Output** window, note the name and path of the output XSLT.</span></span> <span data-ttu-id="aa611-118">Este archivo XSL recibirá el mismo nombre que el archivo de la asignación, pero con la extensión XLS.</span><span class="sxs-lookup"><span data-stu-id="aa611-118">This XSL file will be given the same name as the map file, but with an XSL extension.</span></span> <span data-ttu-id="aa611-119">Para ver el archivo XLS en el Editor de BizTalk, presione CTRL y haga clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="aa611-119">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
6. <span data-ttu-id="aa611-120">En el **salida** ventana, tenga en cuenta el nombre y ruta de acceso del objeto de extensión XML.</span><span class="sxs-lookup"><span data-stu-id="aa611-120">In the **Output** window, note the name and path of the extension object XML.</span></span> <span data-ttu-id="aa611-121">Para ver el archivo XLS en el Editor de BizTalk, presione CTRL y haga clic en el vínculo.</span><span class="sxs-lookup"><span data-stu-id="aa611-121">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa611-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa611-122">See Also</span></span>  
 [<span data-ttu-id="aa611-123">Uso de herramientas de XML en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="aa611-123">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)