---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="f9bc2-101">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f9bc2-101">Importing Binding Files</span></span>

## <a name="overview"></a><span data-ttu-id="f9bc2-102">Información general</span><span class="sxs-lookup"><span data-stu-id="f9bc2-102">Overview</span></span>
<span data-ttu-id="f9bc2-103">Antes de utilizar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9bc2-103">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="f9bc2-104">CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-104">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="f9bc2-105">Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-105">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f9bc2-106">Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-106">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="f9bc2-107">Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como ***** en el archivo de enlaces.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-107">JD Edwards system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f9bc2-108">La implementación sobrescribe la configuración de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-108">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="f9bc2-109">Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-109">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
## <a name="import-the-binding-files"></a><span data-ttu-id="f9bc2-110">Importar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="f9bc2-110">Import the Binding Files</span></span>  
  
1.  <span data-ttu-id="f9bc2-111">En el **iniciar** menú, elija **archivos de programa**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server** Para iniciar la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-111">On the **Start** menu, point to **Program Files**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration** to start the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="f9bc2-112">Expanda Administración de BizTalk Server, **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-112">Expand BizTalk Server Administration, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="f9bc2-113">Haga clic en la aplicación que desee, seleccione **importación**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-113">Right-click the desired application, point to **Import**, and then click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="f9bc2-114">En el **importar enlaces** cuadro de diálogo, busque y seleccione los archivos de enlace y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-114">In the **Import Bindings** dialog box, browse and select the binding files, and then click **Open**.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="f9bc2-115">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="f9bc2-115">Cleaning the Target Computer</span></span>  
<span data-ttu-id="f9bc2-116">Quite los puertos de envío y las ubicaciones de recepción que están enlazados a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f9bc2-116">Remove the send ports and the receive locations that are bound to the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9bc2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9bc2-117">See Also</span></span>  
 <span data-ttu-id="f9bc2-118">[Agregar los artefactos a la administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="f9bc2-118">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="f9bc2-119">Importar JD Edwards OneWorld aplicación</span><span class="sxs-lookup"><span data-stu-id="f9bc2-119">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)