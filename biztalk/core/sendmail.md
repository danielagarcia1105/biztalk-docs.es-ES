---
title: SendMail | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2b9f3be3fd54d34cec1bdfadda723a42f3b6c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005685"
---
# <a name="sendmail"></a><span data-ttu-id="66c03-102">SendMail</span><span class="sxs-lookup"><span data-stu-id="66c03-102">SendMail</span></span>
<span data-ttu-id="66c03-103">El ejemplo SendMail muestra el modo en que puede usar el adaptador del Protocolo simple de transferencia de correo (SMTP) para enviar mensajes de correo electrónico dentro de una orquestación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66c03-103">The SendMail sample demonstrates how you can use the Simple Mail Transfer Protocol (SMTP) adapter to send e-mail messages from within a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="66c03-104">La información dinámica empleada para enviar los mensajes de correo se recupera de un mensaje XML mediante la funcionalidad de promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="66c03-104">Dynamic information used to send the e-mail messages is retrieved from an XML message using property promotion functionality.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="66c03-105">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="66c03-105">What This Sample Does</span></span>  
 <span data-ttu-id="66c03-106">Este ejemplo envía un mensaje de correo electrónico usando información obtenida de las propiedades promocionadas de un mensaje de pedido (PO) XML entrante, mediante la siguiente secuencia de pasos:</span><span class="sxs-lookup"><span data-stu-id="66c03-106">This sample sends an e-mail message using information obtained from properties promoted out of an incoming XML purchase order (PO) message, using the following sequence of steps:</span></span>  

1. <span data-ttu-id="66c03-107">La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera un mensaje de PO XML de entrada.</span><span class="sxs-lookup"><span data-stu-id="66c03-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an input XML PO message.</span></span>  

2. <span data-ttu-id="66c03-108">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orquestación promociona el **PONumber** y **correo electrónico** propiedades para facilitar el acceso en el futuro.</span><span class="sxs-lookup"><span data-stu-id="66c03-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration promotes the **PONumber** and **Email** properties for easier access in the future.</span></span>  

3. <span data-ttu-id="66c03-109">La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa los valores de las propiedades promocionadas para establecer la dirección de destino del puerto de envío dinámico y para establecer el asunto del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="66c03-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration uses the values of the promoted properties to set the destination address of the dynamic send port and to set the subject of the e-mail message.</span></span>  

4. <span data-ttu-id="66c03-110">La orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía el mensaje de correo electrónico construido mediante el adaptador SMTP.</span><span class="sxs-lookup"><span data-stu-id="66c03-110">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration sends the constructed e-mail message through the SMTP adapter.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="66c03-111">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="66c03-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="66c03-112">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail\\</span><span class="sxs-lookup"><span data-stu-id="66c03-112">\<*Samples Path*\>\AdaptersUsage\SendMail\\</span></span>  

 <span data-ttu-id="66c03-113">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="66c03-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                    <span data-ttu-id="66c03-114">Archivos</span><span class="sxs-lookup"><span data-stu-id="66c03-114">File(s)</span></span>                     |                                                                                                         <span data-ttu-id="66c03-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="66c03-115">Description</span></span>                                                                                                         |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="66c03-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span><span class="sxs-lookup"><span data-stu-id="66c03-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span></span> |                                                                         <span data-ttu-id="66c03-117">Proporciona archivos de información de proyectos, soluciones y ensamblados para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66c03-117">Provides project, solution, and assembly information files for this sample.</span></span>                                                                         |
|                  <span data-ttu-id="66c03-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="66c03-118">Cleanup.bat</span></span>                   |              <span data-ttu-id="66c03-119">Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="66c03-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>               |
|     <span data-ttu-id="66c03-120">PropertySchema.xsd, PurchaseOrder.xsd</span><span class="sxs-lookup"><span data-stu-id="66c03-120">PropertySchema.xsd, PurchaseOrder.xsd</span></span>      |                                                           <span data-ttu-id="66c03-121">Proporciona esquemas para las propiedades que se desea promocionar y para el mensaje de PO XML, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="66c03-121">Provides schemas for the properties that you want to promote, and for the XML PO message, respectively.</span></span>                                                           |
|                <span data-ttu-id="66c03-122">ReceiveSend.odx</span><span class="sxs-lookup"><span data-stu-id="66c03-122">ReceiveSend.odx</span></span>                 |   <span data-ttu-id="66c03-123">Proporciona una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que procesa el mensaje de PO XML entrante y envía un mensaje de correo electrónico basado en la información del mensaje.</span><span class="sxs-lookup"><span data-stu-id="66c03-123">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that processes the incoming XML PO message and sends an e-mail message based on information in the message.</span></span>   |
|               <span data-ttu-id="66c03-124">SendMailInput.xml</span><span class="sxs-lookup"><span data-stu-id="66c03-124">SendMailInput.xml</span></span>                |                                                                                 <span data-ttu-id="66c03-125">Contiene un archivo de entrada de ejemplo con un PO especificado mediante XML.</span><span class="sxs-lookup"><span data-stu-id="66c03-125">Contains a sample input file with a PO specified using XML.</span></span>                                                                                 |
|                   <span data-ttu-id="66c03-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="66c03-126">Setup.bat</span></span>                    | <span data-ttu-id="66c03-127">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66c03-127">Builds and initializes this sample.</span></span> <span data-ttu-id="66c03-128">**Nota:** este archivo de instalación crea y enlaza puertos, y así sucesivamente, utilizando un mecanismo diferente que la mayoría de la configuración de los archivos de los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="66c03-128">**Note:**  This setup file creates and binds ports, and so on, using a different mechanism than most of the setup files for the SDK samples.</span></span> <span data-ttu-id="66c03-129">No requiere ningún archivo .xml complementario.</span><span class="sxs-lookup"><span data-stu-id="66c03-129">It does not require a companion .xml file.</span></span> |

### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="66c03-130">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="66c03-130">To build and initialize this sample</span></span>  

1. <span data-ttu-id="66c03-131">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="66c03-131">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="66c03-132">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail</span><span class="sxs-lookup"><span data-stu-id="66c03-132">\<*Samples Path*\>\AdaptersUsage\SendMail</span></span>  

2. <span data-ttu-id="66c03-133">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="66c03-133">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="66c03-134">Crea la siguiente carpeta de entrada para este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66c03-134">Creates the following input folder for this sample:</span></span>  

      <span data-ttu-id="66c03-135">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\SendMail\In</span><span class="sxs-lookup"><span data-stu-id="66c03-135">\<*Samples Path*\>\AdaptersUsage\SendMail\In</span></span>  

   - <span data-ttu-id="66c03-136">Compila el proyecto [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66c03-136">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="66c03-137">Inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66c03-137">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="66c03-138">Debe confirmar que BizTalk no ha informado de ningún error durante el proceso de generación e inicialización antes de intentar ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66c03-138">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="66c03-139">Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la Utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="66c03-139">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="66c03-140">Utilice este par de claves para firmar el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="66c03-140">Use this key pair to sign the resulting assembly.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="66c03-141">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat y elimine todos los puertos de recepción y envío que tengan el prefijo SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span><span class="sxs-lookup"><span data-stu-id="66c03-141">To undo changes made by Setup.bat, run Cleanup.bat and delete all receive and send ports prefixed with SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="66c03-142">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="66c03-142">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

3. <span data-ttu-id="66c03-143">En el **administración de BizTalk Server** de consola, busque el puerto de recepción prefijado por SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span><span class="sxs-lookup"><span data-stu-id="66c03-143">In the **BizTalk Server Administration** console, locate the receive port prefixed by SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="66c03-144">Actualice la ubicación de recepción para que este puerto de recepción señale a un directorio del sistema de archivos para su uso como ubicación de entrada.</span><span class="sxs-lookup"><span data-stu-id="66c03-144">Update the receive location for this receive port to point to a directory on your file system to use as the input location.</span></span>  

4. <span data-ttu-id="66c03-145">Con un programa como el Bloc de notas, modifique el archivo SendMailInput.xml para que el **correo electrónico** elemento especifica una dirección de correo electrónico a la que desea recibir el mensaje de correo electrónico generado por este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="66c03-145">Using a program such as Notepad, modify the file SendMailInput.xml so that the **Email** element specifies a legitimate e-mail address at which you want to receive the e-mail message generated by this sample.</span></span>  

5. <span data-ttu-id="66c03-146">Haga clic en **iniciar**, apunte a **programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="66c03-146">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

6. <span data-ttu-id="66c03-147">En el **administración de BizTalk Server** de consola, expanda el árbol de grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="66c03-147">In the **BizTalk Server Administration** console, expand the BizTalk Group tree.</span></span>  

7. <span data-ttu-id="66c03-148">Expanda el **configuración de plataforma** árbol en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="66c03-148">Expand the **Platform Settings** tree in the left pane.</span></span>  

8. <span data-ttu-id="66c03-149">Expanda el **adaptadores** carpeta, haga clic en el **SMTP** nodo y, a continuación, haga doble clic en el adaptador de SMTP de fila en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="66c03-149">Expand the **Adapters** folder, click the **SMTP** node, and then double-click the SMTP adapter row in the right pane.</span></span>  

9. <span data-ttu-id="66c03-150">En el **SMTP - propiedades de controlador de adaptador** cuadro de diálogo, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66c03-150">In the **SMTP - Adapter Handler Properties** dialog box, click **Properties**.</span></span>  

10. <span data-ttu-id="66c03-151">En el **propiedades de transporte SMTP** cuadro de diálogo el **propiedades** pestaña, proporcione los valores adecuados para el **nombre del servidor SMTP** y **desde (correo electrónico dirección)** propiedades y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66c03-151">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, provide appropriate values for the **SMTP server name** and **From (e-mail address)** properties, and then click **OK**.</span></span>  

     <span data-ttu-id="66c03-152">Estos valores se usarán para construir la dirección de correo electrónico De para cualquier mensaje de correo electrónico enviado a través de este adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="66c03-152">These values will be used to construct the From e-mail address for any e-mail messages sent through this SMTP adapter.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="66c03-153">Si tiene que autenticarse con el servidor SMTP, debe asegurarse de que la dirección de correo electrónico De pertenezca a la misma cuenta que usa para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="66c03-153">If you need to authenticate with your SMTP server, you must ensure that the From e-mail address belongs to the same account that you use for authentication.</span></span>  

11. <span data-ttu-id="66c03-154">Detenga el servicio de BizTalk y después reinícielo (BizTalkServerApplication) para que la orquestación adopte estos cambios.</span><span class="sxs-lookup"><span data-stu-id="66c03-154">Stop and then restart the BizTalk service (BizTalkServerApplication) so that the orchestration will adopt these changes.</span></span>  

### <a name="to-run-this-sample"></a><span data-ttu-id="66c03-155">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="66c03-155">To run this sample</span></span>  

1.  <span data-ttu-id="66c03-156">Coloque una copia del archivo SendMailInput.xml modificado en la carpeta de entrada.</span><span class="sxs-lookup"><span data-stu-id="66c03-156">Put a copy of the modified file SendMailInput.xml into the input folder.</span></span>  

2.  <span data-ttu-id="66c03-157">Observe si llega un mensaje de correo electrónico a la dirección especificada en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="66c03-157">Observe the arrival of an e-mail message to the e-mail address you specified in the previous procedure.</span></span>  

## <a name="see-also"></a><span data-ttu-id="66c03-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="66c03-158">See Also</span></span>  
 [<span data-ttu-id="66c03-159">Ejemplos de adaptadores: uso</span><span class="sxs-lookup"><span data-stu-id="66c03-159">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)