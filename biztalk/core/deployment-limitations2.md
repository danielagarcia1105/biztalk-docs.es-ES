---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 314bffd50e152c1e3141e4f644c60bdbe7a3824a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011037"
---
# <a name="deployment-limitations"></a><span data-ttu-id="5c54d-101">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="5c54d-101">Deployment Limitations</span></span>
<span data-ttu-id="5c54d-102">La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace exportado por el Asistente para la implementación de BizTalk, y se pasa a la administración componente en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="5c54d-102">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="5c54d-103">Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta).</span><span class="sxs-lookup"><span data-stu-id="5c54d-103">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="5c54d-104">A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5c54d-104">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="5c54d-105">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="5c54d-105">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="5c54d-106">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="5c54d-106">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="5c54d-107">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="5c54d-107">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="5c54d-108">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="5c54d-108">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="5c54d-109">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="5c54d-109">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  

## <a name="password-limitation-workaround"></a><span data-ttu-id="5c54d-110">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="5c54d-110">Password Limitation Workaround</span></span>  
 <span data-ttu-id="5c54d-111">Use una de las siguientes soluciones como alternativa para la limitación de contraseña.</span><span class="sxs-lookup"><span data-stu-id="5c54d-111">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="5c54d-112">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="5c54d-112">To work around the password limitation</span></span>  
  
1. <span data-ttu-id="5c54d-113">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="5c54d-113">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="5c54d-114">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="5c54d-114">This is not recommended for security reasons.</span></span>  
  
2. <span data-ttu-id="5c54d-115">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="5c54d-115">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="5c54d-116">Escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5c54d-116">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5c54d-117">Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="5c54d-117">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
   <span data-ttu-id="5c54d-118">**O bien**</span><span class="sxs-lookup"><span data-stu-id="5c54d-118">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="5c54d-119">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="5c54d-119">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="5c54d-120">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="5c54d-120">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="5c54d-121">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5c54d-121">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="5c54d-122">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="5c54d-122">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c54d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c54d-123">See Also</span></span>  
 <span data-ttu-id="5c54d-124">[Agregar los artefactos a administración de BizTalk](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="5c54d-124">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="5c54d-125">Importar el JD Edwards OneWorld app</span><span class="sxs-lookup"><span data-stu-id="5c54d-125">Import the JD Edwards OneWorld app</span></span>](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)