---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 847e66c189cb8fc14014691f95d78b6eec4b45dc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="d1091-101">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="d1091-101">Deployment Limitations</span></span>
<span data-ttu-id="d1091-102">La contraseña del adaptador de transporte se almacena como estrellas (*) en el archivo de enlace exportado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="d1091-102">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="d1091-103">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="d1091-103">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="d1091-104">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="d1091-104">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="d1091-105">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="d1091-105">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="d1091-106">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="d1091-106">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="d1091-107">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="d1091-107">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="d1091-108">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="d1091-108">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="d1091-109">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="d1091-109">Password Limitation Workaround</span></span>  
 <span data-ttu-id="d1091-110">Para solucionar la limitación de contraseña, puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1091-110">To work around the password limitation, you can do the following.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="d1091-111">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="d1091-111">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="d1091-112">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d1091-112">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="d1091-113">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="d1091-113">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="d1091-114">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="d1091-114">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1091-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1091-115">See Also</span></span>  
 [<span data-ttu-id="d1091-116">Importar JD Edwards EnterpriseOne aplicación</span><span class="sxs-lookup"><span data-stu-id="d1091-116">Import the JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)