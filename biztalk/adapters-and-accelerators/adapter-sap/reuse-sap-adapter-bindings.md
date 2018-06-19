---
title: Reutilizar los enlaces del adaptador SAP | Documentos de Microsoft
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
ms.assetid: 5748c22f-20a2-4eb9-ad45-a1bef7290802
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df4c878f8eb6a5e1fd52dfe749b10d1d89716679
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217700"
---
# <a name="reuse-sap-adapter-bindings"></a><span data-ttu-id="2e876-102">Reutilizar los enlaces del adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="2e876-102">Reuse SAP adapter bindings</span></span>
<span data-ttu-id="2e876-103">Un enlace crea una asignación entre un extremo lógico (por ejemplo, un puerto de orquestación o un vínculo de función) y un extremo físico (por ejemplo, un envío y puerto de recepción).</span><span class="sxs-lookup"><span data-stu-id="2e876-103">A binding creates a mapping between a logical endpoint (such as an orchestration port or a role link) and a physical endpoint (such as a send and receive port).</span></span> <span data-ttu-id="2e876-104">Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e876-104">This enables communication between different components of a BizTalk business solution.</span></span> <span data-ttu-id="2e876-105">Puede crear enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e876-105">You can create bindings by using the BizTalk Server Administration console.</span></span>  
  
## <a name="what-is-a-binding-file"></a><span data-ttu-id="2e876-106">¿Qué es un archivo de enlace?</span><span class="sxs-lookup"><span data-stu-id="2e876-106">What is a Binding File?</span></span>  
 <span data-ttu-id="2e876-107">Un archivo de enlace es un archivo XML que contiene información de enlace para cada orquestación de BizTalk en el ámbito de un ensamblado de BizTalk, la aplicación o el grupo.</span><span class="sxs-lookup"><span data-stu-id="2e876-107">A binding file is an XML file that contains binding information for each BizTalk orchestration in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="2e876-108">Describe el archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="2e876-108">The binding file describes:</span></span>  
  
-   <span data-ttu-id="2e876-109">El host al que se enlaza cada orquestación</span><span class="sxs-lookup"><span data-stu-id="2e876-109">The host to which each orchestration is bound</span></span>
  
-   <span data-ttu-id="2e876-110">El nivel de confianza del host</span><span class="sxs-lookup"><span data-stu-id="2e876-110">The trust level of the host</span></span>
  
-   <span data-ttu-id="2e876-111">La configuración para cada puerto de envío, puerto de recepción, ubicación de recepción y entidad a la que se ha configurado</span><span class="sxs-lookup"><span data-stu-id="2e876-111">The settings for each send port, receive port, receive location, and party that has been configured</span></span>
  
 <span data-ttu-id="2e876-112">Puede generar archivos de enlace y, a continuación, aplicar los enlaces que contienen a un ensamblado, la aplicación o el grupo.</span><span class="sxs-lookup"><span data-stu-id="2e876-112">You can generate binding files and then apply the bindings they contain to an assembly, application, or group.</span></span> <span data-ttu-id="2e876-113">Esto evita tener que configurar manualmente los enlaces en diferentes entornos de implementación y acelera la implementación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e876-113">This prevents having to manually configure bindings in different deployment environments and speeds up application deployment.</span></span>  
  
<span data-ttu-id="2e876-114">Un archivo de enlace no se genera automáticamente para un ensamblado, aplicación o el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e876-114">A binding file is not automatically generated for a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="2e876-115">Sin embargo, puede generar un archivo de enlace mediante la exportación de enlaces.</span><span class="sxs-lookup"><span data-stu-id="2e876-115">However, you can generate a binding file by exporting bindings.</span></span> <span data-ttu-id="2e876-116">A continuación, puede importar el archivo de enlace en una aplicación o un grupo.</span><span class="sxs-lookup"><span data-stu-id="2e876-116">You can then import the binding file into an application or group.</span></span>  
  
<span data-ttu-id="2e876-117">Para obtener más información sobre los enlaces y los archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../../core/binding-files-and-application-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="2e876-117">For more information about bindings and about binding files, see [Binding Files and Application Deployment](../../core/binding-files-and-application-deployment.md).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="2e876-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e876-118">Prerequisites</span></span>  
<span data-ttu-id="2e876-119">Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e876-119">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="2e876-120">Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="2e876-120">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>
 
## <a name="export-bindings"></a><span data-ttu-id="2e876-121">Exportar enlaces</span><span class="sxs-lookup"><span data-stu-id="2e876-121">Export bindings</span></span>
<span data-ttu-id="2e876-122">En esta sección se describe cómo exportar enlaces de una aplicación de BizTalk en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="2e876-122">This section describes how to export bindings for a BizTalk application into an XML file.</span></span> <span data-ttu-id="2e876-123">A continuación, puede importar los enlaces desde el archivo XML en otra aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e876-123">You can then import the bindings from the XML file into another BizTalk application.</span></span> <span data-ttu-id="2e876-124">Importar enlaces sobrescriben los enlaces existentes del mismo nombre en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e876-124">Importing bindings overwrites any existing bindings of the same name in the application.</span></span> <span data-ttu-id="2e876-125">También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes.</span><span class="sxs-lookup"><span data-stu-id="2e876-125">You can also add bindings to an application, which does not overwrite existing bindings.</span></span> <span data-ttu-id="2e876-126">Los enlaces que se agregan no se aplican hasta que se importa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e876-126">The bindings that you add do not take effect until you import the application.</span></span>  
  
1.  <span data-ttu-id="2e876-127">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2e876-127">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="2e876-128">Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2e876-128">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2e876-129">Haga clic en la aplicación cuyos enlaces desee exportar, seleccione **exportar**y, a continuación, seleccione **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="2e876-129">Right-click the application whose bindings you want to export, select **Export**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="2e876-130">En el **exportar enlaces** página **exportación a archivo**, escriba la ruta de acceso absoluta del archivo XML que se va a exportar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="2e876-130">On the **Export Bindings** page, in **Export to file**, type the absolute path of the XML file to which to export the bindings.</span></span>  
  
     <span data-ttu-id="2e876-131">Por ejemplo, escriba`C:\Bindings\Application1Bindings.Binding1.xml`</span><span class="sxs-lookup"><span data-stu-id="2e876-131">For example, enter `C:\Bindings\Application1Bindings.Binding1.xml`</span></span>  
  
5.  <span data-ttu-id="2e876-132">Confirme que **exportar todos los enlaces de la aplicación actual** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e876-132">Confirm that **Export all bindings from the current application** is selected.</span></span>  
  
6.  <span data-ttu-id="2e876-133">Para exportar toda la información de entidad para el grupo, seleccione el **información de entidad Global exportar** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="2e876-133">To export all party information for the group, select the **Export Global Party information** check box.</span></span>  
  
7.  <span data-ttu-id="2e876-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e876-134">Select **OK**.</span></span> <span data-ttu-id="2e876-135">Los enlaces se exportan a un archivo XML en la ubicación que especificó.</span><span class="sxs-lookup"><span data-stu-id="2e876-135">The bindings are exported into an XML file in the location that you specified.</span></span>  

## <a name="import-bindings"></a><span data-ttu-id="2e876-136">Importar enlaces</span><span class="sxs-lookup"><span data-stu-id="2e876-136">Import bindings</span></span>
<span data-ttu-id="2e876-137">Importar enlaces mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2e876-137">Import bindings using the BizTalk Server Administration console.</span></span>
  
1.  <span data-ttu-id="2e876-138">Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="2e876-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="2e876-139">Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2e876-139">Expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="2e876-140">Haga clic en la aplicación en la que desea importar los enlaces, seleccione **importar**y, a continuación, seleccione **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="2e876-140">Right-click the application into which you want to import bindings, select **Import**, and then select **Bindings**.</span></span>  
  
4.  <span data-ttu-id="2e876-141">Seleccione el archivo de enlace y, a continuación, seleccione **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="2e876-141">Select the binding file, and then select **Open**.</span></span>  
  
<span data-ttu-id="2e876-142">Los artefactos del archivo de enlace se escriben en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e876-142">The artifacts in the binding file are written to the application.</span></span> <span data-ttu-id="2e876-143">Se muestran en las carpetas correspondientes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e876-143">They display in appropriate folders of the application.</span></span> <span data-ttu-id="2e876-144">Por ejemplo, los puertos de envío se importan como parte de la pantalla de enlaces bajo el **puertos de envío** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2e876-144">For example, the send ports imported as part of the bindings display under the **Send Ports** folder.</span></span>  

## <a name="passwords-are-removed"></a><span data-ttu-id="2e876-145">Se eliminan las contraseñas</span><span class="sxs-lookup"><span data-stu-id="2e876-145">Passwords are removed</span></span>  
<span data-ttu-id="2e876-146">Por motivos de seguridad, cuando se exporta un archivo de enlace [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas de los enlaces del archivo.</span><span class="sxs-lookup"><span data-stu-id="2e876-146">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="2e876-147">Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="2e876-147">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="2e876-148">Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administración de la consola del puerto de envío o ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="2e876-148">You configure passwords in the Transport Properties dialog box of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console for the send port or receive location.</span></span> 

<span data-ttu-id="2e876-149">Para obtener información acerca de cómo especificar el nombre de usuario y contraseñas, consulte [configurar el inicio de sesión en las credenciales para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="2e876-149">For information about specifying user name and passwords, see [Configure the sign in credentials for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e876-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e876-150">See also</span></span>
[<span data-ttu-id="2e876-151">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="2e876-151">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)