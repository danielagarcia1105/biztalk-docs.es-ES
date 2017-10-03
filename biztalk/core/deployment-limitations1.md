---
title: "Implementación Limitations1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="5d0e6-102">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="5d0e6-102">Deployment Limitations</span></span>
<span data-ttu-id="5d0e6-103">La contraseña del adaptador de transporte se almacena como estrellas (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por BizTalk Server y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-103">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="5d0e6-104">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="5d0e6-104">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="5d0e6-105">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-105">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="5d0e6-106">Se trata de una limitación conocida.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-106">This is a known limitation.</span></span> <span data-ttu-id="5d0e6-107">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-107">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="5d0e6-108">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-108">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="5d0e6-109">La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-109">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="5d0e6-110">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-110">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="5d0e6-111">En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-111">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d0e6-112">Al importar un archivo .msi en la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, puede que aparezca un mensaje de error de la importación.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-112">When importing an .msi file in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="5d0e6-113">Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span><span class="sxs-lookup"><span data-stu-id="5d0e6-113">A supported hotfix is available from Microsoft along with a full description of the error at [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="5d0e6-114">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="5d0e6-114">Password Limitation Workaround</span></span>  
 <span data-ttu-id="5d0e6-115">Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="5d0e6-115">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="5d0e6-116">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5d0e6-117">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-117">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="5d0e6-118">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="5d0e6-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="5d0e6-119">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-119">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d0e6-120">Esta solución solo se puede usar si Visual Studio está instalado en el equipo de destino, o si desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-120">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="5d0e6-121">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="5d0e6-121">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0e6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d0e6-122">See Also</span></span>  
 [<span data-ttu-id="5d0e6-123">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="5d0e6-123">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies2.md)