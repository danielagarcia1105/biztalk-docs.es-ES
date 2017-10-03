---
title: "Implementación Limitations2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a><span data-ttu-id="79493-102">Limitaciones de implementación</span><span class="sxs-lookup"><span data-stu-id="79493-102">Deployment Limitations</span></span>
<span data-ttu-id="79493-103">La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por el Asistente para implementar BizTalk y se pasa a la administración componente en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="79493-103">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="79493-104">Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta).</span><span class="sxs-lookup"><span data-stu-id="79493-104">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="79493-105">A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="79493-105">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="79493-106">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="79493-106">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="79493-107">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="79493-107">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="79493-108">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="79493-108">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="79493-109">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="79493-109">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="79493-110">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="79493-110">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79493-111">Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, es posible que aparezca un mensaje de error de importación.</span><span class="sxs-lookup"><span data-stu-id="79493-111">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="79493-112">Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span><span class="sxs-lookup"><span data-stu-id="79493-112">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
## <a name="password-limitation-workaround"></a><span data-ttu-id="79493-113">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="79493-113">Password Limitation Workaround</span></span>  
 <span data-ttu-id="79493-114">Use una de las siguientes soluciones como alternativa para la limitación de contraseña.</span><span class="sxs-lookup"><span data-stu-id="79493-114">Use one of the following as a work-around for the password limitation.</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="79493-115">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="79493-115">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="79493-116">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="79493-116">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="79493-117">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="79493-117">This is not recommended for security reasons.</span></span>  
  
2.  <span data-ttu-id="79493-118">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="79493-118">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="79493-119">Escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="79493-119">Enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79493-120">Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="79493-120">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
 <span data-ttu-id="79493-121">**O bien**</span><span class="sxs-lookup"><span data-stu-id="79493-121">**-OR-**</span></span>  
  
#### <a name="to-work-around-the-password-limitation"></a><span data-ttu-id="79493-122">Para solucionar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="79493-122">To work around the password limitation</span></span>  
  
1.  <span data-ttu-id="79493-123">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="79493-123">Use Enterprise Single Sign-On instead of using passwords.</span></span>  
  
     <span data-ttu-id="79493-124">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="79493-124">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="79493-125">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="79493-125">Verify the Logical system and the Transmit and Receive services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79493-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="79493-126">See Also</span></span>  
 <span data-ttu-id="79493-127">[Cómo establecer las propiedades de transporte de OneWorld JD Edwards](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="79493-127">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="79493-128">Implementación de puertos y ensamblados</span><span class="sxs-lookup"><span data-stu-id="79493-128">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies4.md)