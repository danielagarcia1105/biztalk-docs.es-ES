---
title: Administrar (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4234614cc9f00809f8922999ae96e6f254989c6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="manage-biztalk-server-sample"></a><span data-ttu-id="0cb42-102">Administrar (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="0cb42-102">Manage (BizTalk Server Sample)</span></span>
<span data-ttu-id="0cb42-103">El ejemplo para administrar inicio de sesión único (SSO) muestra cómo se construyen archivos .xml que se pueden usar con la utilidad de línea de comandos ssomanage.exe para llevar a cabo los siguientes tipos de operaciones de administración:</span><span class="sxs-lookup"><span data-stu-id="0cb42-103">The Manage Single Sign-On (SSO) sample demonstrates how to construct .xml files that you can use with the ssomanage.exe command-line utility to perform the following types of administration operations:</span></span>  
  
-   <span data-ttu-id="0cb42-104">Actualizar información global en el nivel de sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="0cb42-104">Update global information at the SSO system level</span></span>  
  
-   <span data-ttu-id="0cb42-105">Crear aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="0cb42-105">Create affiliate applications</span></span>  
  
-   <span data-ttu-id="0cb42-106">Crear asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="0cb42-106">Create user mappings</span></span>  
  
 <span data-ttu-id="0cb42-107">Para obtener información conceptual acerca de Enterprise Single Sign-On, vea [mediante SSO](../core/using-sso.md).</span><span class="sxs-lookup"><span data-stu-id="0cb42-107">For conceptual information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
 <span data-ttu-id="0cb42-108">Para obtener un ejemplo que muestra cómo configurar mediante programación el SSO, como la creación de aplicaciones afiliadas y asignaciones de usuario, consulte [HTTPSSO (ejemplo de BizTalk Server)](../core/httpsso-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0cb42-108">For a sample that shows how to programmatically configure SSO, such as creating affiliate applications and user mappings, see [HTTPSSO (BizTalk Server Sample)](../core/httpsso-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="0cb42-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cb42-109">What This Sample Does</span></span>  
 <span data-ttu-id="0cb42-110">Este ejemplo incluye pares de XSD y archivos .xml de ejemplo para cada uno de estos tipos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0cb42-110">This sample includes pairs of XSD and sample .xml files for each of these types of operations.</span></span> <span data-ttu-id="0cb42-111">Los valores de los archivos .xml de ejemplo no son válidos.</span><span class="sxs-lookup"><span data-stu-id="0cb42-111">The values in the sample .xml files are not valid.</span></span> <span data-ttu-id="0cb42-112">Debe efectuar cambios en los valores para adecuarlos a sus necesidades específicas.</span><span class="sxs-lookup"><span data-stu-id="0cb42-112">You must make changes to the values that are appropriate to your specific requirements.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="0cb42-113">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cb42-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="0cb42-114">*\<Ejemplos de ruta de acceso\>*\SSO\Manage\\</span><span class="sxs-lookup"><span data-stu-id="0cb42-114">*\<Samples Path\>*\SSO\Manage\\</span></span>  
  
 <span data-ttu-id="0cb42-115">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="0cb42-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="0cb42-116">Archivos</span><span class="sxs-lookup"><span data-stu-id="0cb42-116">File(s)</span></span>|<span data-ttu-id="0cb42-117">Description</span><span class="sxs-lookup"><span data-stu-id="0cb42-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0cb42-118">AffiliateApplication.xml, GlobalInfo.xml, UserMapping.xml</span><span class="sxs-lookup"><span data-stu-id="0cb42-118">AffiliateApplication.xml, GlobalInfo.xml, UserMapping.xml</span></span>|<span data-ttu-id="0cb42-119">Archivos .xml de ejemplo que puede, después de modificarlos, pasar como argumentos a la utilidad de línea de comandos ssomanage.exe.</span><span class="sxs-lookup"><span data-stu-id="0cb42-119">Sample .xml files that you can, after modification, pass as arguments to the command-line utility ssomanage.exe.</span></span>|  
|<span data-ttu-id="0cb42-120">AffiliateApplication.xsd, GlobalInfo.xsd, UserMapping.xsd</span><span class="sxs-lookup"><span data-stu-id="0cb42-120">AffiliateApplication.xsd, GlobalInfo.xsd, UserMapping.xsd</span></span>|<span data-ttu-id="0cb42-121">Archivos de esquema para los archivos .xml correspondientes que proporcionan descripciones completas de sus posibles elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="0cb42-121">Schema files for the corresponding .xml files, providing complete descriptions of their possible elements and attributes.</span></span> <span data-ttu-id="0cb42-122">Puede usarlos para validar los archivos .xml correspondientes recibidos desde otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="0cb42-122">You can use these files to validate corresponding .xml files received from other sources.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="0cb42-123">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cb42-123">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="0cb42-124">Debido a que este ejemplo consta únicamente de archivos de lenguaje de definición de esquemas XML (XSD) y de archivos .xml, éstos últimos se pueden modificar y pasar a la utilidad de línea de comandos ssomanage.exe, no hay nada para crear.</span><span class="sxs-lookup"><span data-stu-id="0cb42-124">Because this sample consists of only XML Schema definition language (XSD) and .xml files, the latter of which you can modify and then pass to the command-line utility ssomanage.exe, there is nothing to build in this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="0cb42-125">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cb42-125">Running This Sample</span></span>  
 <span data-ttu-id="0cb42-126">Este ejemplo incluye archivos .xml de ejemplo para ejecutar la utilidad de línea de comandos ssomanage.exe en los tres modos diferentes que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="0cb42-126">This sample includes sample .xml files for running the command-line utility ssomanage.exe in the following three different modes:</span></span>  
  
-   <span data-ttu-id="0cb42-127">**Actualizar información global en el nivel de sistema SSO.**</span><span class="sxs-lookup"><span data-stu-id="0cb42-127">**Update global information at the SSO system level.**</span></span> <span data-ttu-id="0cb42-128">Para realizar este tipo de operación, efectúe los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cb42-128">To perform this type of operation, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="0cb42-129">Edite el archivo GlobalInfo.xml como sea necesario para la configuración concreta.</span><span class="sxs-lookup"><span data-stu-id="0cb42-129">Edit the file GlobalInfo.xml as required for your specific configuration.</span></span>  
  
    2.  <span data-ttu-id="0cb42-130">Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos adecuados, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cb42-130">Run the ssomanage.exe command-line utility with the appropriate arguments, as follows:</span></span>  
  
        ```  
        ssomanage –updatedb GlobalInfo.xml  
        ```  
  
     <span data-ttu-id="0cb42-131">Asegúrese de que edita los valores en el archivo GlobalInfo.xml para que coincidan con el entorno.</span><span class="sxs-lookup"><span data-stu-id="0cb42-131">Ensure that you edit the values in the file GlobalInfo.xml to match your environment.</span></span> <span data-ttu-id="0cb42-132">Por ejemplo, la cuenta de administrador de SSO debe ser una cuenta de Windows válida.</span><span class="sxs-lookup"><span data-stu-id="0cb42-132">For example, the SSO Admin account must be a valid Windows account.</span></span> <span data-ttu-id="0cb42-133">Tanto la cuenta de administrador de SSO como la cuenta de administrador afiliado de SSO deben ser cuentas del grupo de dominios globales de Windows.</span><span class="sxs-lookup"><span data-stu-id="0cb42-133">Both the SSO Admin account and SSO Affiliate Admin account must be Windows Global Domain Group accounts.</span></span>  
  
-   <span data-ttu-id="0cb42-134">**Crear aplicaciones afiliadas.**</span><span class="sxs-lookup"><span data-stu-id="0cb42-134">**Create affiliate applications.**</span></span> <span data-ttu-id="0cb42-135">Para realizar este tipo de operación, efectúe los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cb42-135">To perform this type of operation, perform the following steps:</span></span>  
  
-   <span data-ttu-id="0cb42-136">Edite el archivo AffiliateApplication.xml como sea necesario para la configuración concreta.</span><span class="sxs-lookup"><span data-stu-id="0cb42-136">Edit the file AffiliateApplication.xml as required for your specific configuration.</span></span>  
  
    -   <span data-ttu-id="0cb42-137">Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos apropiados, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0cb42-137">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
        ```  
        ssomanage –createapps AffiliateApplication.xml  
        ```  
  
     <span data-ttu-id="0cb42-138">Puede crear varias aplicaciones afiliadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="0cb42-138">You can create more than one affiliate application at the same time.</span></span>  
  
-   <span data-ttu-id="0cb42-139">**Crear asignaciones de usuarios.**</span><span class="sxs-lookup"><span data-stu-id="0cb42-139">**Create user mappings.**</span></span> <span data-ttu-id="0cb42-140">Para realizar este tipo de operación, efectúe los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0cb42-140">To perform this type of operation, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="0cb42-141">Edite el archivo UserMapping.xml como sea necesario para la configuración concreta.</span><span class="sxs-lookup"><span data-stu-id="0cb42-141">Edit the file UserMapping.xmlas required for your specific configuration.</span></span>  
  
    2.  <span data-ttu-id="0cb42-142">Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos apropiados, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0cb42-142">Run the command-line utility ssomanage.exe with the appropriate arguments, as follows:</span></span>  
  
        ```  
        ssomanage –createmappings UserMapping.xml  
        ```  
  
     <span data-ttu-id="0cb42-143">Puede crear varias asignaciones para una o más aplicaciones afiliadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="0cb42-143">You can create more than one mapping for one or more affiliate applications at the same time.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="0cb42-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cb42-144">Comments</span></span>  
 <span data-ttu-id="0cb42-145">Después de realizar cambios en los archivos .xml de ejemplo proporcionados con este ejemplo, en concreto los cambios que implican incluir información confidencial en los archivos, asegúrese de que estos archivos están bien protegidos en su sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="0cb42-145">After making changes to the sample .xml files provided with this sample, especially where such changes involve including sensitive information in the files, ensure that these files are well protected in your file system.</span></span> <span data-ttu-id="0cb42-146">Por ejemplo, asegúrese de que no se colocan por equivocación en una carpeta de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="0cb42-146">For example, ensure that they are not inadvertently placed in a folder that is shared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb42-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cb42-147">See Also</span></span>  
 [<span data-ttu-id="0cb42-148">SSO (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="0cb42-148">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)