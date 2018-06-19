---
title: Cómo configurar un archivo de clave de ensamblado de nombre seguro | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec807cf6b596f7e89f607ebeb56700c59134c211
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968810"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="aff4f-102">Cómo configurar un archivo de clave de ensamblado de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="aff4f-102">How to Configure a Strong Name Assembly Key File</span></span>
<span data-ttu-id="aff4f-103">En el proceso de implementación de una solución de BizTalk, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] primero genera los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aff4f-103">In the process of deploying a BizTalk solution, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] first builds the assemblies.</span></span> <span data-ttu-id="aff4f-104">El proceso de implementación necesita que cada ensamblado esté firmado de forma segura.</span><span class="sxs-lookup"><span data-stu-id="aff4f-104">The deployment process requires that each assembly is strongly signed.</span></span> <span data-ttu-id="aff4f-105">Fuertemente puede firmar los ensamblados asociando el proyecto con un archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="aff4f-105">You can strongly sign your assemblies by associating the project with a strong name assembly key file.</span></span> <span data-ttu-id="aff4f-106">Antes de implementar una solución desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] si aún no ha generado un archivo de clave de ensamblado de nombre seguro, use el procedimiento siguiente para ello y para asignarlo a cada proyecto de la solución.</span><span class="sxs-lookup"><span data-stu-id="aff4f-106">If you haven't already done so, before deploying a solution from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], use the following procedure to generate a strong name assembly key file and assign it to each project in the solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aff4f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aff4f-107">Prerequisites</span></span>  
 <span data-ttu-id="aff4f-108">Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="aff4f-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrator's group.</span></span> <span data-ttu-id="aff4f-109">Además, la cuenta debe tener permisos de escritura en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="aff4f-109">In addition, your account must have Write permissions on the global assembly cache (GAC).</span></span> <span data-ttu-id="aff4f-110">La cuenta de administradores del equipo local cuenta con este permiso.</span><span class="sxs-lookup"><span data-stu-id="aff4f-110">The Administrators account on the local computer has this permission.</span></span>  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="aff4f-111">Para configurar un archivo de clave de ensamblado de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="aff4f-111">To configure a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="aff4f-112">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="aff4f-112">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="aff4f-113">En el símbolo del sistema, desde la carpeta donde desea almacenar el archivo de clave, escriba el comando siguiente y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="aff4f-113">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="aff4f-114">**sn /k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="aff4f-114">**sn /k**  *file_name* **.snk**</span></span>  
  
     <span data-ttu-id="aff4f-115">Ejemplo: **sn /k ErrorHandling.snk**</span><span class="sxs-lookup"><span data-stu-id="aff4f-115">Example: **sn /k ErrorHandling.snk**</span></span>  
  
     <span data-ttu-id="aff4f-116">Un mensaje de confirmación, **escribe en el par de claves** \< *file_name*\>**.snk** `,` muestra en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aff4f-116">A confirmation message, **Key pair written to** \<*file_name*\>**.snk**`,` displays on the command line.</span></span>  
  
3.  <span data-ttu-id="aff4f-117">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en el proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aff4f-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the project and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="aff4f-118">Haga clic en el **firma** y a **examinar** en el **elegir un archivo de clave de nombre seguro** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="aff4f-118">Click the **Signing** tab and choose **Browse** in the **Choose a strong name key file** drop down box.</span></span>  
  
5.  <span data-ttu-id="aff4f-119">Busque el archivo de clave y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="aff4f-119">Browse to the key file and click it.</span></span> <span data-ttu-id="aff4f-120">Haga clic en **abiertos**y, a continuación, cierre las propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="aff4f-120">Click **Open**, and then close the project properties.</span></span>  
  
6.  <span data-ttu-id="aff4f-121">Repita los pasos del 3 al 6 para cada proyecto de la solución que desea implementar con este archivo de clave de ensamblado de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="aff4f-121">Repeat steps 3 through 6 for each project in the solution that you want to deploy using this strong name assembly key file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff4f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aff4f-122">See Also</span></span>  
 [<span data-ttu-id="aff4f-123">Implementación de ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aff4f-123">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)