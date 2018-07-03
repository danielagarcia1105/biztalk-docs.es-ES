---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9d12874ef6042580183f407afc811a9d7f6e0fc9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009869"
---
# <a name="deployment-limitations"></a><span data-ttu-id="1e8ba-101">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="1e8ba-101">Deployment Limitations</span></span>

## <a name="overview"></a><span data-ttu-id="1e8ba-102">Información general</span><span class="sxs-lookup"><span data-stu-id="1e8ba-102">Overview</span></span>
<span data-ttu-id="1e8ba-103">La contraseña del adaptador de transporte se almacena con asteriscos (******) en el archivo de enlace exportado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y pasa al componente de administración con el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-103">The Transport Adapter password is stored as stars (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="1e8ba-104">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="1e8ba-105">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="1e8ba-106">La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-106">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="1e8ba-107">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="1e8ba-108">En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-108">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="1e8ba-109">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="1e8ba-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="1e8ba-110">Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="1e8ba-110">To work around this password limitation, you can use one of the following methods:</span></span>  
  
- <span data-ttu-id="1e8ba-111">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-111">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
  > [!CAUTION]
  >  <span data-ttu-id="1e8ba-112">Esta práctica no se recomienda por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-112">This practice is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="1e8ba-113">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="1e8ba-113">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="1e8ba-114">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-114">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1e8ba-115">Esta solución solo puede utilizarse si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-115">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
  <span data-ttu-id="1e8ba-116">-o bien-</span><span class="sxs-lookup"><span data-stu-id="1e8ba-116">-or-</span></span>  
  
- <span data-ttu-id="1e8ba-117">Use el inicio de sesión único (SSO) empresarial en lugar de utilizar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-117">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span>  
  
   <span data-ttu-id="1e8ba-118">El uso de la opción SSO requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-118">Using the SSO option requires an import of the binding file.</span></span>  
  
  <span data-ttu-id="1e8ba-119">Compruebe el sistema lógico y la transmisión y recepción de servicios.</span><span class="sxs-lookup"><span data-stu-id="1e8ba-119">Verify the logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8ba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8ba-120">See Also</span></span>  
[<span data-ttu-id="1e8ba-121">Importar enlaces y limitaciones</span><span class="sxs-lookup"><span data-stu-id="1e8ba-121">Import bindings & limitations</span></span>](../core/deploying-biztalk-adapter-for-peoplesoft-enterprise.md)