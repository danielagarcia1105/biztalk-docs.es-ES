---
title: 'Paso 1: Asignar un nombre seguro al ensamblado de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d388fc725b8aaeec4cbfa80c23bd5e2a1b42a27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963866"
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a><span data-ttu-id="9d3c6-102">Paso 1: Asignar un nombre seguro al ensamblado de Contoso</span><span class="sxs-lookup"><span data-stu-id="9d3c6-102">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>
<span data-ttu-id="9d3c6-103">En este paso, creará y asignará un nombre seguro para el ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-103">In this step, you create and assign a strong name for your BizTalk assembly.</span></span> <span data-ttu-id="9d3c6-104">Un nombre seguro garantiza la exclusividad de un ensamblado mediante la asignación de una firma digital y un par de claves exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-104">A strong name guarantees the uniqueness of an assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="9d3c6-105">Además, un nombre seguro proporciona una comprobación de integridad para garantizar que el contenido del ensamblado no ha cambiado desde que se compiló por última vez.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-105">Additionally, a strong name provides an integrity check to guarantee that the content of the assembly has not changed since you last built it.</span></span>  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a><span data-ttu-id="9d3c6-106">Para crear un archivo de clave de ensamblado de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="9d3c6-106">To create a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="9d3c6-107">Inicie un **símbolo del sistema de Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-107">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="9d3c6-108">En el símbolo del sistema, vaya a la ubicación de la solución de Contoso.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-108">At the command prompt, move to the location of the Contoso solution.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d3c6-109">De forma predeterminada, la ubicación de la solución de Contoso es  *\<unidad\>*: \Documents and Settings\\*\<nombre de usuario\>* \My Documentos\Visual Studio \<versión\>\Projects.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-109">By default, the location of the Contoso solution is *\<drive\>*:\Documents and Settings\\*\<user name\>* \My Documents\Visual Studio \<version\>\Projects.</span></span>  
  
3.  <span data-ttu-id="9d3c6-110">En el símbolo del sistema, escriba **sn -k FabConPriceAvail.sn**y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-110">At the command prompt, type **sn -k FabConPriceAvail.snk**, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="9d3c6-111">En el símbolo del sistema, escriba **xit**y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-111">At the command prompt, type **Exit**, and then press **Enter**.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="9d3c6-112">Para asignar un nombre seguro al ensamblado</span><span class="sxs-lookup"><span data-stu-id="9d3c6-112">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="9d3c6-113">En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **ContosoPriceAndAvailability** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-113">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9d3c6-114">En las páginas de propiedades, haga clic en **Firmar** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-114">In the Property Pages, click **Signing** in the left pane.</span></span>  
  
3.  <span data-ttu-id="9d3c6-115">En el panel derecho, seleccione **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-115">In the right pane, select **Sign the assembly**.</span></span>  
  
4.  <span data-ttu-id="9d3c6-116">Haga clic en **Examinar** en el campo Seleccione un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-116">Click **Browse** in the Choose the strong name key file field.</span></span>  
  
5.  <span data-ttu-id="9d3c6-117">Busque la carpeta del proyecto, seleccione el archivo **FabConPriceAvail.snk** que creó anteriormente y, a continuación, haga clic en **Abiertos**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-117">Locate your project folder, select the **FabConPriceAvail.snk** file you created earlier, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="9d3c6-118">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-118">Click **OK** to save the changes.</span></span>  
  
7.  <span data-ttu-id="9d3c6-119">En el Explorador de soluciones, haga clic con el botón secundario en el proyecto **ContosoPriceAndAvailability** y, a continuación, haga clic en **Compilación**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-119">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, and then click **Build**.</span></span> <span data-ttu-id="9d3c6-120">Después de finalizar la compilación, vuelva a hacer clic con el botón secundario en el proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="9d3c6-120">After the build has succeeded, right-click the project again, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3c6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3c6-121">See Also</span></span>  
 [<span data-ttu-id="9d3c6-122">Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de la consulta/respuesta de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="9d3c6-122">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)