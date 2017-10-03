---
title: "Implementación Limitations4 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, deployment limitations
- deployment, limitations
ms.assetid: 1312627e-9de2-461e-a8c4-66a9d41bb714
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d8e33c7274ab0f95c6d7fff1bf9746ac86e420
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="11569-102">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="11569-102">Deployment Limitations</span></span>
<span data-ttu-id="11569-103">La contraseña del adaptador de transporte se almacena como estrellas (*) en el archivo de enlace exportado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="11569-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="11569-104">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="11569-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="11569-105">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="11569-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="11569-106">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="11569-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="11569-107">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="11569-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="11569-108">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="11569-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="11569-109">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="11569-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11569-110">Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, puede que aparezca un mensaje de error de la importación.</span><span class="sxs-lookup"><span data-stu-id="11569-110">When importing an .msi file in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="11569-111">Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087).</span><span class="sxs-lookup"><span data-stu-id="11569-111">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkId=196087](http://go.microsoft.com/fwlink/?LinkId=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="11569-112">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="11569-112">Password Limitation Workaround</span></span>  
 <span data-ttu-id="11569-113">Para solucionar la limitación de contraseña, puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11569-113">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="11569-114">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="11569-114">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="11569-115">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="11569-115">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="11569-116">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="11569-116">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="11569-117">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="11569-117">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11569-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="11569-118">See Also</span></span>  
 [<span data-ttu-id="11569-119">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="11569-119">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies3.md)