---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: ac85aec2f1153d5117c95627e573ec563d58dbc2
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="931ae-101">Implementar puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="931ae-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="931ae-102">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="931ae-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="931ae-103">BizTalk Server exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="931ae-103">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="931ae-104">Puede usar BizTalk Server para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="931ae-104">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="931ae-105">Implementar o quitar los ensamblados de BizTalk Server en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="931ae-105">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="931ae-106">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="931ae-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="931ae-107">Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="931ae-107">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="931ae-108">El adaptador de Microsoft BizTalk para JD Edwards OneWorld solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="931ae-108">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="931ae-109">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="931ae-109">Visual Studio is not required on the production computer.</span></span>  
  
