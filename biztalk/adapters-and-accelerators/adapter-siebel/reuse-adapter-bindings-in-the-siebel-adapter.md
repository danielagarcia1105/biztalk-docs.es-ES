---
title: Volver a usar los enlaces del adaptador en el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding file, definition
- adapter bindings, reusing
ms.assetid: 1dc17b7a-5397-43f4-b19e-9c50fb0e97ff
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a85346b44a88b5776e9f586ddc56675f8ef9ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007045"
---
# <a name="reuse-adapter-bindings-in-the-siebel-adapter"></a><span data-ttu-id="07210-102">Volver a usar los enlaces del adaptador en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="07210-102">Reuse adapter bindings in the Siebel adapter</span></span>
<span data-ttu-id="07210-103">Un enlace crea una asignación entre un extremo lógico, como un puerto de orquestación o un vínculo de rol, y un extremo físico, como una entidad o un puerto de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="07210-103">A binding creates a mapping between a logical endpoint, such as an orchestration port or a role link, and a physical endpoint, such as a send and receive port or party.</span></span> <span data-ttu-id="07210-104">Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07210-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="07210-105">Puede crear enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="07210-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="07210-106">¿Qué es un archivo de enlace?</span><span class="sxs-lookup"><span data-stu-id="07210-106">What is a binding file?</span></span>  
<span data-ttu-id="07210-107">Un archivo de enlace es un archivo XML que contiene información de enlace para cada orquestación de BizTalk en el ámbito de un ensamblado de BizTalk, la aplicación o el grupo.</span><span class="sxs-lookup"><span data-stu-id="07210-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="07210-108">Describe el archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="07210-108">The binding file describes:</span></span>  
  
- <span data-ttu-id="07210-109">El host al que se enlaza cada orquestación</span><span class="sxs-lookup"><span data-stu-id="07210-109">The host to which each orchestration is bound</span></span>
  
- <span data-ttu-id="07210-110">El nivel de confianza del host</span><span class="sxs-lookup"><span data-stu-id="07210-110">The trust level of the host</span></span>
  
- <span data-ttu-id="07210-111">La configuración para cada puerto de envío, puerto de recepción, ubicación de recepción y entidad que se ha configurado</span><span class="sxs-lookup"><span data-stu-id="07210-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
  <span data-ttu-id="07210-112">Puede generar archivos de enlace y, a continuación, aplicar los enlaces que contienen a un ensamblado, aplicación o grupo.</span><span class="sxs-lookup"><span data-stu-id="07210-112">You can generate binding files and then apply the bindings that they contain to an assembly, application, or group.</span></span> <span data-ttu-id="07210-113">Esto evita tener que configurar manualmente los enlaces en diferentes entornos de implementación y acelera la implementación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07210-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
  <span data-ttu-id="07210-114">No se genera automáticamente un archivo de enlace de un ensamblado, aplicación o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07210-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="07210-115">Sin embargo, puede generar un archivo de enlace mediante la exportación de enlaces.</span><span class="sxs-lookup"><span data-stu-id="07210-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="07210-116">A continuación, puede importar el archivo de enlace a una aplicación o grupo.</span><span class="sxs-lookup"><span data-stu-id="07210-116">You can then import the binding file into an application or group.</span></span>  
  
  <span data-ttu-id="07210-117">Para obtener más información acerca de los enlaces y los archivos de enlace, consulte [archivos de enlace e implementación de aplicaciones](../../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="07210-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
 
  > [!NOTE]
  >  <span data-ttu-id="07210-118">No se genera automáticamente un archivo de enlace de un ensamblado, aplicación o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07210-118">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="07210-119">Pero puede generar un archivo de enlace mediante la exportación de enlaces.</span><span class="sxs-lookup"><span data-stu-id="07210-119">But you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="07210-120">A continuación, puede importar el archivo de enlace a una aplicación o grupo.</span><span class="sxs-lookup"><span data-stu-id="07210-120">You can then import the binding file into an application or group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="07210-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="07210-121">Prerequisites</span></span>  
<span data-ttu-id="07210-122">Inicie sesión en ON, una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07210-122">Sign in ith an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="07210-123">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="07210-123">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>

 
## <a name="export-bindings"></a><span data-ttu-id="07210-124">Exportar enlaces</span><span class="sxs-lookup"><span data-stu-id="07210-124">Export bindings</span></span>
<span data-ttu-id="07210-125">En esta sección se describe cómo exportar enlaces para una aplicación de BizTalk en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="07210-125">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="07210-126">A continuación, puede importar los enlaces del archivo XML en otra aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="07210-126">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="07210-127">Importar enlaces sobrescriben los enlaces existentes del mismo nombre en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07210-127">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="07210-128">También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes.</span><span class="sxs-lookup"><span data-stu-id="07210-128">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="07210-129">Los enlaces que se agregan no se aplican hasta que se importa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07210-129">The bindings that you add do not take effect until you import the application.</span></span>  
  
1. <span data-ttu-id="07210-130">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="07210-130">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="07210-131">Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="07210-131">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="07210-132">Haga clic en la aplicación cuyos enlaces desee exportar, seleccione **exportar**y, a continuación, seleccione **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="07210-132">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="07210-133">En el **exportar enlaces** página **exportación a archivo**, escriba la ruta de acceso absoluta del archivo XML que se va a exportar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="07210-133">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
    <span data-ttu-id="07210-134">Por ejemplo, escriba `C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="07210-134">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5. <span data-ttu-id="07210-135">Confirme que **exportar todos los enlaces de la aplicación actual** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="07210-135">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6. <span data-ttu-id="07210-136">Para exportar toda la información de entidad para el grupo, seleccione el **información de entidad Global exportar** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="07210-136">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7. <span data-ttu-id="07210-137">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07210-137">Select **OK**.</span></span> <span data-ttu-id="07210-138">Los enlaces se exportan a un archivo XML en la ubicación que especificó.</span><span class="sxs-lookup"><span data-stu-id="07210-138">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="07210-139">Importar enlaces</span><span class="sxs-lookup"><span data-stu-id="07210-139">Import bindings</span></span>
<span data-ttu-id="07210-140">Importar enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="07210-140">Import bindings using the BizTalk Server Administration console.</span></span>
  
1. <span data-ttu-id="07210-141">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="07210-141">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="07210-142">Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="07210-142">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="07210-143">Haga clic en la aplicación en la que desea importar los enlaces, seleccione **importar**y, a continuación, seleccione **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="07210-143">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4. <span data-ttu-id="07210-144">Seleccione el archivo de enlace y, a continuación, seleccione **abierto**.</span><span class="sxs-lookup"><span data-stu-id="07210-144">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="07210-145">Los artefactos del archivo de enlace se escriben en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07210-145">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="07210-146">Se muestran en las carpetas correspondientes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07210-146">They display in appropriate folders of the application.</span></span> <span data-ttu-id="07210-147">Por ejemplo, los puertos de envío se importan como parte de la presentación de enlaces bajo el **puertos de envío** carpeta.</span><span class="sxs-lookup"><span data-stu-id="07210-147">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="07210-148">Las contraseñas se quitan</span><span class="sxs-lookup"><span data-stu-id="07210-148">Passwords are removed</span></span>  
<span data-ttu-id="07210-149">Por motivos de seguridad, al exportar un archivo de enlace, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas para los enlaces del archivo.</span><span class="sxs-lookup"><span data-stu-id="07210-149">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="07210-150">Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="07210-150">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="07210-151">Configurar las contraseñas en el cuadro de diálogo Propiedades de transporte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administración de la consola para el puerto de envío o ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="07210-151">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="07210-152">Para obtener información acerca de cómo especificar el nombre de usuario y contraseñas, consulte [configurar el inicio de sesión en las credenciales para el Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="07210-152">For information about specifying user name and passwords, see [Configure the sign in credentials for the Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-sign-in-credentials-for-the-siebel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07210-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="07210-153">See also</span></span>
[<span data-ttu-id="07210-154">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="07210-154">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)