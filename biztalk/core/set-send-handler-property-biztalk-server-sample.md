---
title: "Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783f465feff207ae1759ea358b0b848ccc0f4c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="set-send-handler-property-biztalk-server-sample"></a><span data-ttu-id="7c632-102">Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="7c632-102">Set Send Handler Property (BizTalk Server Sample)</span></span>
<span data-ttu-id="7c632-103">El ejemplo para establecer propiedad de controlador de envío muestra cómo establecer la información de configuración de XML para un controlador de envío del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="7c632-103">The Set Send Handler Property sample demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7c632-104">Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="7c632-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="7c632-105">La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.</span><span class="sxs-lookup"><span data-stu-id="7c632-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="7c632-106">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c632-106">What This Sample Does</span></span>  
 <span data-ttu-id="7c632-107">La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="7c632-107">The Visual Basic Scripting Edition (VBScript) script in the script file that constitutes this sample shows how to perform the following operations using the BizTalk Server WMI provider:</span></span>  
  
-   <span data-ttu-id="7c632-108">A partir de un nombre de controlador de envío, consultar una lista de controladores de envío coincidentes.</span><span class="sxs-lookup"><span data-stu-id="7c632-108">Given a send handler name, query for a list of matching send handlers.</span></span>  
  
-   <span data-ttu-id="7c632-109">Establecer la información de configuración de XML para un controlador de envío de SMTP.</span><span class="sxs-lookup"><span data-stu-id="7c632-109">Set the XML configuration information for an SMTP send handler.</span></span>  
  
-   <span data-ttu-id="7c632-110">Administrar errores tales como la devolución al usuario de información significativa.</span><span class="sxs-lookup"><span data-stu-id="7c632-110">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="7c632-111">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c632-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="7c632-112">Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:</span><span class="sxs-lookup"><span data-stu-id="7c632-112">The sample files are located in the following SDK location:</span></span>  
  
 <span data-ttu-id="7c632-113">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Set Property\ del controlador de envío</span><span class="sxs-lookup"><span data-stu-id="7c632-113">\<*Samples Path*\>\Admin\WMI\Set Send Handler Property\\</span></span>  
  
 <span data-ttu-id="7c632-114">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="7c632-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="7c632-115">Archivos</span><span class="sxs-lookup"><span data-stu-id="7c632-115">File(s)</span></span>|<span data-ttu-id="7c632-116">Description</span><span class="sxs-lookup"><span data-stu-id="7c632-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c632-117">En la carpeta \VBScript:</span><span class="sxs-lookup"><span data-stu-id="7c632-117">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="7c632-118">ConfigureSMTP.vbs</span><span class="sxs-lookup"><span data-stu-id="7c632-118">ConfigureSMTP.vbs</span></span>|<span data-ttu-id="7c632-119">El archivo VBScript toma parámetros que especifican un controlador de envío de SMTP y una dirección de remite de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7c632-119">VBScript file that takes parameters that specify an SMTP send handler and a From e-mail address.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7c632-120">Crear e inicializar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c632-120">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="7c632-121">El ejemplo para establecer propiedad de controlador de envío consta de un archivo único VBScript que no necesita generar o inicializar.</span><span class="sxs-lookup"><span data-stu-id="7c632-121">The Set Send Handler Property sample consists of a single VBScript file that you do not need to build or initialize.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="7c632-122">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c632-122">Running This Sample</span></span>  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a><span data-ttu-id="7c632-123">Para ejecutar el ejemplo para establecer propiedad de controlador de envío</span><span class="sxs-lookup"><span data-stu-id="7c632-123">To run the Set Send Handler Property sample</span></span>  
  
1.  <span data-ttu-id="7c632-124">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="7c632-124">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="7c632-125">\<*Ejemplos de ruta de acceso*\>\Admin\WMI\Set Property\VBScript\ del controlador de envío</span><span class="sxs-lookup"><span data-stu-id="7c632-125">\<*Samples Path*\>\Admin\WMI\Set Send Handler Property\VBScript\\</span></span>  
  
2.  <span data-ttu-id="7c632-126">Ejecute el archivo ConfigureSMTP.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="7c632-126">Run the file ConfigureSMTP.vbs using the cscript program, passing the following command-line argument:</span></span>  
  
    -   <span data-ttu-id="7c632-127">**\<** ***SMTPServerName* \>.**</span><span class="sxs-lookup"><span data-stu-id="7c632-127">**\<** ***SMTPServerName* \>.**</span></span> <span data-ttu-id="7c632-128">El nombre del servidor SMTP que se usará para enviar correo.</span><span class="sxs-lookup"><span data-stu-id="7c632-128">The name of the SMTP server that will be used to send mail.</span></span>  
  
    -   <span data-ttu-id="7c632-129">**\<** ***FromEmailAddress* \>.**</span><span class="sxs-lookup"><span data-stu-id="7c632-129">**\<** ***FromEmailAddress* \>.**</span></span> <span data-ttu-id="7c632-130">Una dirección de correo electrónico que se usará como remite.</span><span class="sxs-lookup"><span data-stu-id="7c632-130">An e-mail address that will be used as the From address.</span></span>  
  
         <span data-ttu-id="7c632-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7c632-131">For example:</span></span>  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a><span data-ttu-id="7c632-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c632-132">Comments</span></span>  
 <span data-ttu-id="7c632-133">Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.</span><span class="sxs-lookup"><span data-stu-id="7c632-133">All tasks that you can perform in the BizTalk Server Administration console can also be performed by using script that accesses the Windows WMI object model.</span></span>  
  
 <span data-ttu-id="7c632-134">El archivo de secuencias de comandos ConfigureSMTP.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="7c632-134">The script file ConfigureSMTP.vbs contains detailed comments with further explanation about the operations that it performs.</span></span> <span data-ttu-id="7c632-135">Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span><span class="sxs-lookup"><span data-stu-id="7c632-135">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c632-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c632-136">See Also</span></span>  
 [<span data-ttu-id="7c632-137">Admin\WMI (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="7c632-137">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)