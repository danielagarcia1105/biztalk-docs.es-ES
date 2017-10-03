---
title: "Implementación Limitations3 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, password limitations
- transport adapter password
ms.assetid: 79cd330f-ecc5-430e-9d79-608593d873cb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0d01947e0769189c269a1853e7fda0e11cedb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="b517b-102">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="b517b-102">Deployment Limitations</span></span>
<span data-ttu-id="b517b-103">La contraseña del adaptador de transporte se almacena con asteriscos (******) en el archivo de enlace exportado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y pasa al componente de administración con el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="b517b-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="b517b-104">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="b517b-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="b517b-105">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="b517b-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="b517b-106">La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="b517b-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="b517b-107">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="b517b-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="b517b-108">En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="b517b-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b517b-109">Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, puede que aparezca un mensaje de error de la importación.</span><span class="sxs-lookup"><span data-stu-id="b517b-109">When importing an .msi file in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="b517b-110">Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span><span class="sxs-lookup"><span data-stu-id="b517b-110">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="b517b-111">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="b517b-111">Password Limitation Workaround</span></span>  
 <span data-ttu-id="b517b-112">Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b517b-112">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="b517b-113">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="b517b-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="b517b-114">No se recomienda por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b517b-114">This practice is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="b517b-115">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="b517b-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="b517b-116">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="b517b-116">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b517b-117">Esta solución solo puede utilizarse si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="b517b-117">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
 <span data-ttu-id="b517b-118">-O bien-</span><span class="sxs-lookup"><span data-stu-id="b517b-118">-or-</span></span>  
  
-   <span data-ttu-id="b517b-119">Use el inicio de sesión único (SSO) empresarial en lugar de utilizar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="b517b-119">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
     <span data-ttu-id="b517b-120">El uso de la opción SSO requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="b517b-120">Using the SSO option requires an import of the binding file.</span></span>  
  
 <span data-ttu-id="b517b-121">Compruebe el sistema lógico y la transmisión y recepción de servicios.</span><span class="sxs-lookup"><span data-stu-id="b517b-121">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b517b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b517b-122">See Also</span></span>  
 [<span data-ttu-id="b517b-123">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="b517b-123">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies5.md)