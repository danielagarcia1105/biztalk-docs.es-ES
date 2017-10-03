---
title: Ejecutar una consulta de ejemplo de OneWorld JD Edwards | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35d05dfe719a9b199d7422f99ef80e888126f01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="87786-102">Ejecución de una consulta de ejemplo de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-102">Executing a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="87786-103">El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld (JDEOW) desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="87786-104">Este adaptador pertenece a un grupo de ocho adaptadores de línea empresarial (LOB) que Microsoft distribuye para su uso con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span>  
  
 <span data-ttu-id="87786-105">Esta es la segunda parte del trabajo práctico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="87786-106">En la primera parte (Práctica 1), obtuvo acceso manualmente a los datos en el sistema JD Edwards OneWorld sin ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otra tecnología de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="87786-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="87786-107">En esta parte (Práctica 2), creará una orquestación de BizTalk como parte de un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="87786-108">Configurará puertos en esta orquestación para usar el adaptador de JD Edwards OneWorld con el objetivo de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87786-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="87786-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="87786-110">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87786-110">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   <span data-ttu-id="87786-111">Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87786-111">Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]</span></span>  
  
-   <span data-ttu-id="87786-112">Software JD Edwards OneWorld Client</span><span class="sxs-lookup"><span data-stu-id="87786-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="87786-113">Conectividad de red para un sistema JD Edwards OneWorld en otro servidor</span><span class="sxs-lookup"><span data-stu-id="87786-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="87786-114">Adaptadores de Microsoft BizTalk para aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="87786-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87786-115">Para obtener información sobre cómo instalar y configurar Microsoft BizTalk Adapters para aplicaciones empresariales, vea [HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=196039" \t "_blank" http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039).</span><span class="sxs-lookup"><span data-stu-id="87786-115">For information about installing and configuring Microsoft BizTalk Adapters for Enterprise Applications, see [HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=196039" \t "_blank" http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039).</span></span> <span data-ttu-id="87786-116">En este documento se incluye información de configuración clave para los adaptadores de JD Edwards, PeopleSoft, JD Edwards OneWorld, TIBCO y Siebel LOB.</span><span class="sxs-lookup"><span data-stu-id="87786-116">This document includes key configuration information for the JD Edwards, PeopleSoft, JD Edwards OneWorld, TIBCO, and Siebel LOB adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="87786-117">Práctica 2: ejecución de un consulta de ejemplo de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-117">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="87786-118">En esta práctica, ejecutará una **obtener** operación en el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-118">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-119">Específicamente, realizará las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="87786-119">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="87786-120">Comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-120">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="87786-121">Configurar un puerto de envío de JD Edwards OneWorld en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87786-121">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="87786-122">Crear un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="87786-122">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="87786-123">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="87786-123">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="87786-124">Probar la aplicación y ver la salida XML</span><span class="sxs-lookup"><span data-stu-id="87786-124">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="87786-125">Usará el adaptador de JD Edwards OneWorld para obtener acceso a los datos del sistema JD Edwards OneWorld desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-125">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="87786-126">Este adaptador le permite procesar objetos de JD Edwards OneWorld mediante solicitudes y respuestas ejecutadas por una orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-126">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="87786-127">Se encuentran disponibles diversos métodos para objetos de esquema.</span><span class="sxs-lookup"><span data-stu-id="87786-127">Many methods are available for a schema object.</span></span> <span data-ttu-id="87786-128">Este laboratorio muestra cómo utilizar el **Address Book MBF** método.</span><span class="sxs-lookup"><span data-stu-id="87786-128">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="87786-129">Antes de ejecutar una solicitud de servicio, debe crear esquemas de solicitud y respuesta de servicio para el objeto específico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-129">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="87786-130">El Asistente para agregar elementos generados/agregar adaptador crea estos esquemas al interrogar directamente al objeto de metadatos de compatibilidad en JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-130">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="87786-131">Esta práctica, describen los pasos necesarios para crear esquemas para la **Address Book MBF** método y procesar una consulta.</span><span class="sxs-lookup"><span data-stu-id="87786-131">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="procedures-for-lab-2--executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="87786-132">Procedimientos de la Práctica 2: ejecución de un consulta de ejemplo de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-132">Procedures for Lab 2- Executing a JD Edwards OneWorld Sample Query</span></span>  
  
### <a name="verifying-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="87786-133">Comprobación de los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-133">Verifying the JD Edwards OneWorld Prerequisites</span></span>  
 <span data-ttu-id="87786-134">Antes de comenzar a crear un proyecto de BizTalk para usarlo con el adaptador de JD Edwards OneWorld, debe asegurarse de que los archivos y el adaptador están configurados correctamente para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-134">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-135">En el equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el adaptador de JD Edwards OneWorld se comunica con el sistema JD Edwards OneWorld a través de la interfaz Java.</span><span class="sxs-lookup"><span data-stu-id="87786-135">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>  
  
 <span data-ttu-id="87786-136">Cuatro archivos son necesarios para el acceso a la interfaz adecuada para un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld: Connector.jar, Kernel.jar, BTSLIBinterop.jar y JDEJAccess.jar.</span><span class="sxs-lookup"><span data-stu-id="87786-136">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
-   <span data-ttu-id="87786-137">Los archivos Connector.jar y Kernel.jar están incluidos en el sistema JD Edwards OneWorld y se obtienen desde un administrador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-137">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="87786-138">Estos archivos se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="87786-138">These files are located in the C:\JDEOWJars folder.</span></span>  
  
-   <span data-ttu-id="87786-139">El sistema JD Edwards OneWorld genera el archivo BTSLIBinterop.jar al seguir las instrucciones incluidas en la Guía de instalación para adaptadores.</span><span class="sxs-lookup"><span data-stu-id="87786-139">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="87786-140">Este archivo se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="87786-140">This file is located in the C:\JDEOWJars folder.</span></span>  
  
-   <span data-ttu-id="87786-141">El archivo JDEJAccess.jar forma parte del adaptador JDEOW y se incluye en la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="87786-141">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="87786-142">De forma predeterminada, se encuentra en C:\Program Files\Microsoft BizTalk Adapters para Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="87786-142">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="87786-143">Edwards OneWorld® \Classes carpeta.</span><span class="sxs-lookup"><span data-stu-id="87786-143">Edwards OneWorld®\Classes folder.</span></span>  
  
##### <a name="to-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="87786-144">Procedimiento para comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-144">To verify the JD Edwards OneWorld prerequisites</span></span>  
  
1.  <span data-ttu-id="87786-145">Asegúrese de que los archivos Connector.jar, Kernel.jar y BTSLIBinterop.jar existan en la carpeta C:\JDEOWJars del equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-145">Ensure that the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
2.  <span data-ttu-id="87786-146">Asegúrese de que el archivo JDEJAccess.jar exista en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en el C:\Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="87786-146">Ensure that the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="87786-147">Edwards OneWorld® \Classes carpeta.</span><span class="sxs-lookup"><span data-stu-id="87786-147">Edwards OneWorld®\Classes folder.</span></span>  
  
3.  <span data-ttu-id="87786-148">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="87786-148">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
### <a name="configuring-biztalk-send-ports"></a><span data-ttu-id="87786-149">Configuración de puertos de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="87786-149">Configuring BizTalk Send Ports</span></span>  
 <span data-ttu-id="87786-150">A continuación, comprobará si el adaptador de JD Edwards OneWorld está instalado y creará el puerto de envío de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-150">Now you will verify that the JD Edwards OneWorld adapter is installed and create the JD Edwards OneWorld send port.</span></span>  
  
##### <a name="to-verify-that-the-jd-edwards-oneworld-adapter-is-installed-in-includepragueincludesprague-mdmd"></a><span data-ttu-id="87786-151">Procedimiento para comprobar que el adaptador de JD Edwards OneWorld está instalado en [!INCLUDE[prague](../includes/prague-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87786-151">To verify that the JD Edwards OneWorld adapter is installed in [!INCLUDE[prague](../includes/prague-md.md)]</span></span>  
  
1.  <span data-ttu-id="87786-152">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="87786-152">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="87786-153">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda  **Configuración de plataforma**y, a continuación, expanda **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="87786-153">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
     <span data-ttu-id="87786-154">Asegúrese de que el **JDE_OneWorld** adaptador está instalado y en la lista.</span><span class="sxs-lookup"><span data-stu-id="87786-154">Ensure that the **JDE_OneWorld** adapter is installed and on the list.</span></span> <span data-ttu-id="87786-155">Si no está instalado el adaptador de JD Edwards OneWorld, instale los adaptadores de Microsoft BizTalk Adapters for Enterprise Applications (vea la sección anterior "Requisitos previos").</span><span class="sxs-lookup"><span data-stu-id="87786-155">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="87786-156">Una vez instalados los adaptadores, haga clic en **adaptadores** y, a continuación, haga clic en **nuevo - adaptador** para instalar el adaptador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-156">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="87786-157">Deberá reiniciar la instancia del host para que esto surta efecto.</span><span class="sxs-lookup"><span data-stu-id="87786-157">You will have to restart the host instance for this to take effect.</span></span>  
  
##### <a name="to-create-the-jd-edwards-oneworld-send-port"></a><span data-ttu-id="87786-158">Procedimiento para crear el puerto de envío de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-158">To create the JD Edwards OneWorld send port</span></span>  
  
1.  <span data-ttu-id="87786-159">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda  **Aplicaciones**y, a continuación, expanda **BizTalk Application 1**.</span><span class="sxs-lookup"><span data-stu-id="87786-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="87786-160">Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**. Escriba los siguientes valores para estos campos:</span><span class="sxs-lookup"><span data-stu-id="87786-160">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="87786-161">**Nombre:**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="87786-161">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="87786-162">**Tipo:**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="87786-162">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="87786-163">**Controlador de envío:**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="87786-163">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="87786-164">**Canalización de envío:**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="87786-164">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="87786-165">**La canalización de recepción:**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="87786-165">**Receive pipeline:**  `XMLReceive`</span></span>  
  
3.  <span data-ttu-id="87786-166">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-166">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="87786-167">**Host:** \<escriba su nombre de host JDEOW ></span><span class="sxs-lookup"><span data-stu-id="87786-167">**Host:** \<enter your JDEOW host name></span></span>  
  
    2.  <span data-ttu-id="87786-168">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="87786-168">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="87786-169">**Entorno JDEdwards:** \<entran en el entorno de JDEOW ></span><span class="sxs-lookup"><span data-stu-id="87786-169">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
    4.  <span data-ttu-id="87786-170">**Archivos JAR de JDEdwards:** \<escriba la ruta de acceso completa de archivos JAR ></span><span class="sxs-lookup"><span data-stu-id="87786-170">**JDEdwards JAR files:** \<enter full path of JAR files></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="87786-171">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-171">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="87786-172">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="87786-172">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="87786-173">**Nombre de usuario:** \<escriba su nombre de usuario de JD Edwards ></span><span class="sxs-lookup"><span data-stu-id="87786-173">**User Name:** \<enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
4.  <span data-ttu-id="87786-174">Haga clic en **Aceptar** dos veces para cerrar el **propiedades de puerto de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="87786-174">Click **OK** twice to close the **Send Port Properties** dialog box.</span></span>  
  
### <a name="creating-a-biztalk-orchestration-project"></a><span data-ttu-id="87786-175">Creación de un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="87786-175">Creating a BizTalk Orchestration Project</span></span>  
 <span data-ttu-id="87786-176">A continuación, creará un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y configurará una orquestación en el proyecto para gestionar la comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-176">Now you will create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-177">Agregará puertos de recepción y envío, generará el proyecto y, a continuación, lo implementará.</span><span class="sxs-lookup"><span data-stu-id="87786-177">You will add send and receive ports, build the project, and then deploy the project.</span></span>  
  
##### <a name="to-create-the-biztalk-orchestration-project-in-visual-studio"></a><span data-ttu-id="87786-178">Procedimiento para crear el proyecto de orquestación de BizTalk en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87786-178">To create the BizTalk orchestration project in Visual Studio</span></span>  
  
1.  <span data-ttu-id="87786-179">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y cree un nuevo proyecto de BizTalk en la carpeta C:\LABS.</span><span class="sxs-lookup"><span data-stu-id="87786-179">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="87786-180">En el menú **Archivo** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="87786-180">On the **File** menu, click **New**.</span></span> <span data-ttu-id="87786-181">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="87786-181">The **New Project** dialog box appears.</span></span> <span data-ttu-id="87786-182">En la consola de administración de **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="87786-182">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="87786-183">Escriba `JDE_OW_Test` como nombre único del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87786-183">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="87786-184">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, haga clic en **Agregar**y, a continuación, en **Agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="87786-184">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="87786-185">En el panel de categorías, seleccione **agregar metadatos de adaptador**, en el panel Plantillas, seleccione **agregar metadatos de adaptador**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="87786-185">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="87786-186">En el Asistente para agregar adaptador, seleccione el **JD Edwards OneWorld** adaptador, seleccione el **JDE_OneWorldPort** puerto de envío que creó en el procedimiento anterior y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-186">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  <span data-ttu-id="87786-187">En el **seleccionar servicios para importar** página abierta **JD Edwards OneWorld**.</span><span class="sxs-lookup"><span data-stu-id="87786-187">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="87786-188">La comunicación con el sistema JDEOW se establece a través del adaptador mediante el uso del programa BrowsingAgent.</span><span class="sxs-lookup"><span data-stu-id="87786-188">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="87786-189">El programa BrowsingAgent muestra los servicios que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="87786-189">The BrowsingAgent returns the following services.</span></span>  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  <span data-ttu-id="87786-190">Expanda **CALLBSFN** y desplácese hacia abajo hasta **N0100041 - Address Book MBF**.</span><span class="sxs-lookup"><span data-stu-id="87786-190">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="87786-191">Seleccione N0100041 y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="87786-191">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="87786-192">En el Explorador de soluciones, hay una nueva orquestación de BizTalk con dos nuevos archivos de esquema asociados.</span><span class="sxs-lookup"><span data-stu-id="87786-192">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="87786-193">Estos archivos los crea el Asistente para agregar adaptador.</span><span class="sxs-lookup"><span data-stu-id="87786-193">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="87786-194">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 <span data-ttu-id="87786-195">La orquestación acepta como entrada del adaptador de archivo un archivo XML con formato para el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-195">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-196">A su vez, usa el adaptador de JD Edwards OneWorld para enviar el archivo XML al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-196">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-197">El sistema JD Edwards OneWorld procesa la consulta y genera un archivo XML de salida que contiene los resultados.</span><span class="sxs-lookup"><span data-stu-id="87786-197">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="87786-198">Este archivo XML regresa a la orquestación mediante el adaptador de JD Edwards OneWorld y el adaptador de archivo escribe el archivo XML en la ubicación de salida del disco.</span><span class="sxs-lookup"><span data-stu-id="87786-198">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="87786-199">Para completar la orquestación, debe crear y configurar puertos para recibir y enviar los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="87786-199">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="87786-200">Primero, configure el puerto de recepción que usará el adaptador de archivo para introducir el archivo XML que contiene la consulta en la orquestación del disco.</span><span class="sxs-lookup"><span data-stu-id="87786-200">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
##### <a name="to-configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="87786-201">Procedimiento para configurar un puerto de recepción para aceptar el archivo XML de entrada</span><span class="sxs-lookup"><span data-stu-id="87786-201">To configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="87786-202">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-202">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="87786-203">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="87786-203">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="87786-204">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="87786-204">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="87786-205">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-205">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="87786-206">En el **propiedades de puerto** escriba `JDE_File_In` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-206">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="87786-207">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-207">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="87786-208">**Nombre de tipo de puerto**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="87786-208">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="87786-209">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="87786-209">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="87786-210">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="87786-210">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="87786-211">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-211">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="87786-212">**Dirección de puerto de comunicación**: **Siempre recibiré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="87786-212">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="87786-213">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="87786-213">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="87786-214">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="87786-214">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="87786-215">Por último, cree un puerto de envío/recepción para enviar al sistema JD Edwards OneWorld el archivo de entrada XML inicial que contiene la consulta.</span><span class="sxs-lookup"><span data-stu-id="87786-215">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-216">Este puerto también recibirá un archivo XML de salida que contiene los resultados de la consulta correspondiente a la llamada realizada al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-216">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
##### <a name="to-configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="87786-217">Procedimiento para configurar un puerto de envío/recepción para establecer la conexión con JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="87786-217">To configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="87786-218">En el archivo BizTalk Orchestration.odx, haga clic en la superficie para puerto derecha y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="87786-218">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="87786-219">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="87786-219">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="87786-220">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-220">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="87786-221">En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="87786-221">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="87786-222">En **tipos de puertos disponibles**, seleccione **JD_OW_Test.N0100041**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-222">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  <span data-ttu-id="87786-223">Seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-223">Select the following property values:</span></span>  
  
     <span data-ttu-id="87786-224">**Dirección de puerto de comunicación**: **enviaré una solicitud y recibiré una respuesta**</span><span class="sxs-lookup"><span data-stu-id="87786-224">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="87786-225">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="87786-225">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="87786-226">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="87786-226">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="87786-227">En la superficie del puerto, verá el puerto y los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="87786-227">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="87786-228">Por último, configure el puerto de envío que usará el adaptador de archivo para enviar al disco el archivo XML que contiene los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="87786-228">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
##### <a name="to-configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="87786-229">Procedimiento para configurar un puerto de envío para enviar el archivo XML al disco</span><span class="sxs-lookup"><span data-stu-id="87786-229">To configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="87786-230">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="87786-230">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="87786-231">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="87786-231">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="87786-232">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-232">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="87786-233">En el **propiedades de puerto** escriba `JDE_FileOut` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87786-233">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="87786-234">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-234">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="87786-235">**Nombre de tipo de puerto**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="87786-235">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="87786-236">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="87786-236">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="87786-237">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="87786-237">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="87786-238">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-238">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="87786-239">**Dirección de puerto de comunicación**: **Siempre enviaré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="87786-239">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="87786-240">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="87786-240">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="87786-241">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="87786-241">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="87786-242">En la superficie del puerto se muestran los puertos nuevos y los métodos disponibles para los servicios JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-242">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="87786-243">Más adelante, especificará el adaptador de JD Edwards OneWorld para enviar y recibir archivos provenientes del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-243">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="87786-244">El **JDE_File_In** y **JDE_File_Out** puertos que acaba de crear necesidad de tipos de mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="87786-244">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
##### <a name="to-assign-message-types-to-the-ports"></a><span data-ttu-id="87786-245">Procedimiento para asignar tipos de mensajes a los puertos</span><span class="sxs-lookup"><span data-stu-id="87786-245">To assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="87786-246">En la superficie de puerto de la izquierda, en la **JDE_File_In** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="87786-246">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="87786-247">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBF**.</span><span class="sxs-lookup"><span data-stu-id="87786-247">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="87786-248">En la superficie de puerto de la izquierda, en la **JDE_File_Out** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="87786-248">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="87786-249">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBFResponse**.</span><span class="sxs-lookup"><span data-stu-id="87786-249">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="87786-250">Inserte dos **enviar** y dos formas **recepción** formas en la orquestación para vincular a los puertos.</span><span class="sxs-lookup"><span data-stu-id="87786-250">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
##### <a name="to-add-send-and-receive-shapes"></a><span data-ttu-id="87786-251">Procedimiento para agregar formas de envío y recepción</span><span class="sxs-lookup"><span data-stu-id="87786-251">To add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="87786-252">Arrastre un componente **Recepción** desde el cuadro de herramientas y suéltelo inmediatamente debajo del inicio de la orquestación (el círculo verde).</span><span class="sxs-lookup"><span data-stu-id="87786-252">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="87786-253">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `Get_File` para el **nombre**y establezca **activar** a `true`.</span><span class="sxs-lookup"><span data-stu-id="87786-253">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="87786-254">De este modo se activará la orquestación cuando se reciba un documento entrante en este puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="87786-254">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="87786-255">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **GetFileReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="87786-255">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="87786-256">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `SendToJDEOW` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="87786-256">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="87786-257">Arrastre un **recepción** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **SendToJDEOWSend** forma.</span><span class="sxs-lookup"><span data-stu-id="87786-257">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="87786-258">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `JDEOW_Resp` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="87786-258">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="87786-259">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **JDEOW_RespReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="87786-259">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="87786-260">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `FileToDisk` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="87786-260">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  <span data-ttu-id="87786-261">Conectar el **JDE_FileIn** puerto a la **GetFileReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="87786-261">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="87786-262">Conectar el **JDE_FileOut** puerto a la **FileToDiskReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="87786-262">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="87786-263">Vaya a **Vista orquestación** y expanda **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="87786-263">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="87786-264">Cambie el identificador para **Message_1** a `MsgToJDEOW`y para **Message_2** a`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="87786-264">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="87786-265">Resalte el **SendToJDEOWSend** componente y establezca su **mensaje** propiedad **MsgToJDEOW**.</span><span class="sxs-lookup"><span data-stu-id="87786-265">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="87786-266">Resalte el **JDEOW_RespReceive** componente y establezca su **mensaje** propiedad **JDEOW_Resp**.</span><span class="sxs-lookup"><span data-stu-id="87786-266">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="87786-267">Conectar **SendToJDEOW** a la **solicitar** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="87786-267">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="87786-268">Conectar **JDEOW_Resp** a la **respuesta** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="87786-268">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
### <a name="building-and-deploying-the-project"></a><span data-ttu-id="87786-269">Generación e implementación del proyecto</span><span class="sxs-lookup"><span data-stu-id="87786-269">Building and Deploying the Project</span></span>  
 <span data-ttu-id="87786-270">Ahora, el proyecto de BizTalk está completo y puede generarlo e implementarlo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87786-270">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
##### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="87786-271">Procedimiento para generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="87786-271">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="87786-272">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="87786-272">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="87786-273">Para generar el proyecto, es necesario un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="87786-273">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="87786-274">En el símbolo del sistema, escriba lo siguiente para crear un archivo de clave de nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="87786-274">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="87786-275">**sn -k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="87786-275">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="87786-276">En el Explorador de soluciones, haga clic en el **JD_OW_Test** del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="87786-276">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="87786-277">Haga clic en la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="87786-277">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="87786-278">Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="87786-278">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="87786-279">Busque y seleccione el archivo de clave: **labs.snk**y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="87786-279">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="87786-280">Haga clic en la pestaña **Implementación** del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="87786-280">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="87786-281">Establecer el **nombre de la aplicación** a `JDE_OW_Test`.</span><span class="sxs-lookup"><span data-stu-id="87786-281">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="87786-282">En el Explorador de soluciones, haga clic en el **JDE_OW_Test** del proyecto y, a continuación, haga clic en **compilar.**</span><span class="sxs-lookup"><span data-stu-id="87786-282">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. <span data-ttu-id="87786-283">Cuando la compilación finalice correctamente, haga clic en el **XX_JD Edwards OneWorldQuery** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="87786-283">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="87786-284">En la ventana de salida, aparecerá:</span><span class="sxs-lookup"><span data-stu-id="87786-284">In the output window the following output will be displayed:</span></span>  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
### <a name="testing-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="87786-285">Prueba de la aplicación y visualización de la salida XML</span><span class="sxs-lookup"><span data-stu-id="87786-285">Testing the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="87786-286">A continuación, probará la aplicación que acaba de crear e implementar.</span><span class="sxs-lookup"><span data-stu-id="87786-286">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="87786-287">Creará el archivo XML que inicia el proceso de orquestación y, a continuación, configurará carpetas para recibir y enviar archivos XML en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87786-287">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="87786-288">Una vez que haya configurado la aplicación, la ejecutará y visualizará los archivos XML que devuelve la orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-288">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
##### <a name="to-generate-the-xml-file-for-the-query"></a><span data-ttu-id="87786-289">Procedimiento para generar el archivo XML de la consulta</span><span class="sxs-lookup"><span data-stu-id="87786-289">To generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="87786-290">En el Explorador de soluciones, haga doble clic en **N0100041Service_N0100041.xsd** para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="87786-290">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="87786-291">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="87786-291">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="87786-292">Para **Nombre de archivo de instancia de salida** , escriba la siguiente ruta de acceso y nombre de archivo para el XML del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="87786-292">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="87786-293">Haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="87786-293">Click **OK.**</span></span> <span data-ttu-id="87786-294">En la ventana Propiedades, seleccione  **\<esquema >** y establecer **referencia raíz:** a `AddressBookMasterMBF`.</span><span class="sxs-lookup"><span data-stu-id="87786-294">In the Properties window, select **\<Schema>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="87786-295">Esto hará que el XML generado sólo incluirá el **consulta** xml.</span><span class="sxs-lookup"><span data-stu-id="87786-295">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  <span data-ttu-id="87786-296">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="87786-296">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="87786-297">Esto genera el **Sample.xml** archivo.</span><span class="sxs-lookup"><span data-stu-id="87786-297">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="87786-298">Este archivo se colocará en la ubicación de recepción como entrada del adaptador para iniciar el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-298">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
##### <a name="to-configure-and-start-the-biztalk-application"></a><span data-ttu-id="87786-299">Procedimiento para configurar e iniciar la aplicación BizTalk</span><span class="sxs-lookup"><span data-stu-id="87786-299">To configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="87786-300">Configure carpetas para recibir los archivos entrantes y enviar los salientes.</span><span class="sxs-lookup"><span data-stu-id="87786-300">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="87786-301">Vaya a **C:\LABS\JDE_OW_Test** y cree dos nuevas subcarpetas denominadas `FileIn` y `FileOut`.</span><span class="sxs-lookup"><span data-stu-id="87786-301">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="87786-302">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda**administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="87786-302">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="87786-303">Haga clic en **JDE_OW_Test**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="87786-303">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  <span data-ttu-id="87786-304">Seleccione **Orchestration_1** y haga clic en el cuadro desplegable **Host** .</span><span class="sxs-lookup"><span data-stu-id="87786-304">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="87786-305">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="87786-305">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="87786-306">En **puertos de recepción**, haga clic en  **\<ninguno >**.</span><span class="sxs-lookup"><span data-stu-id="87786-306">Under **Receive Ports**, click **\<None>**.</span></span> <span data-ttu-id="87786-307">En la lista desplegable, seleccione **Nuevo puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="87786-307">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="87786-308">Para **nombre**, tipo `JDE_FileIn_Port`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="87786-308">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="87786-309">Aparecerá un cuadro de mensaje que indica que debe designar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="87786-309">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="87786-310">Haga clic en **Aceptar**y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="87786-310">Click **OK**, and then click **New**.</span></span>  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  <span data-ttu-id="87786-311">Escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-311">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="87786-312">**Nombre**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="87786-312">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="87786-313">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="87786-313">**Type**: **File**</span></span>  
  
     <span data-ttu-id="87786-314">**Controlador de recepción**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="87786-314">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="87786-315">**Canalización de recepción**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="87786-315">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  <span data-ttu-id="87786-316">Haga clic en **configurar**, tipo `C:\LABS\JDE_OW_Test\FileIn` para **carpeta recepción**y, a continuación, haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="87786-316">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. <span data-ttu-id="87786-317">Haga clic en  **\<ninguno >** para **JDE_OW_Port** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="87786-317">Click **\<None>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="87786-318">Seleccione **nuevo puerto de envío** y, a continuación, seleccione o escriba los valores para las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="87786-318">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="87786-319">**Nombre**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="87786-319">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="87786-320">**Tipo de**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="87786-320">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="87786-321">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="87786-321">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="87786-322">**Canalizaciones**: **XMLTransmit** y **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="87786-322">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="87786-323">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-323">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="87786-324">**Host:** \<escriba su nombre de host JDEOW ></span><span class="sxs-lookup"><span data-stu-id="87786-324">**Host:** \<enter your JDEOW host name></span></span>  
  
     <span data-ttu-id="87786-325">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="87786-325">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="87786-326">**Entorno JDEdwards:** \<entran en el entorno de JDEOW ></span><span class="sxs-lookup"><span data-stu-id="87786-326">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
     <span data-ttu-id="87786-327">**Archivos JAR de JDEdwards:**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="87786-327">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="87786-328">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-328">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="87786-329">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="87786-329">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="87786-330">**Nombre de usuario:**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="87786-330">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. <span data-ttu-id="87786-331">Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="87786-331">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="87786-332">En el Applicationwindow configurar, haga clic en  **\<ninguno >** para **JDE_FileOut** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="87786-332">In the Configure Applicationwindow, click **\<None>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="87786-333">Seleccione **Nuevo puerto de envío** y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="87786-333">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="87786-334">**Nombre**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="87786-334">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="87786-335">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="87786-335">**Type**: **File**</span></span>  
  
     <span data-ttu-id="87786-336">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="87786-336">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="87786-337">**Canalización de envío**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="87786-337">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="87786-338">Haga clic en **configurar** y tipo`C:\Labs\JDE_OW_Test\FileOut` para **carpeta de destino.**</span><span class="sxs-lookup"><span data-stu-id="87786-338">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="87786-339">. Mantenga **%MessageID%.xml** en **Nombre de archivo** because this results in a unique file en each message.</span><span class="sxs-lookup"><span data-stu-id="87786-339">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. <span data-ttu-id="87786-340">Haga clic en **Aceptar** tres veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="87786-340">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="87786-341">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic con el **JDE_OW_Test** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="87786-341">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
##### <a name="to-test-the-orchestration"></a><span data-ttu-id="87786-342">Procedimiento para probar la orquestación</span><span class="sxs-lookup"><span data-stu-id="87786-342">To test the orchestration</span></span>  
  
1.  <span data-ttu-id="87786-343">En el **C:\Labs\JDE_OW_Test** directorio el **Sample.xml** archivo aparecerá como:</span><span class="sxs-lookup"><span data-stu-id="87786-343">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  <span data-ttu-id="87786-344">Editar la **Sample.xml** archivo para quitar todo excepto la **cActionCode** y **mnAddressBookNumber** elementos.</span><span class="sxs-lookup"><span data-stu-id="87786-344">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  <span data-ttu-id="87786-345">Para el **cActionCode** elemento inserte la letra `i`.</span><span class="sxs-lookup"><span data-stu-id="87786-345">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="87786-346">Para **mnAddressBookNumber** insertar el número `500`.</span><span class="sxs-lookup"><span data-stu-id="87786-346">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="87786-347">Guarde los cambios y copie el archivo en el **C:\Labs\JDE_OW_Test\FileIn** carpeta.</span><span class="sxs-lookup"><span data-stu-id="87786-347">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="87786-348">Se trata de la ubicación de recepción que inicia el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-348">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="87786-349">En unos segundos, debe aparecer un archivo XML en el **C:\Labs\JDE_OW_Test\FileOut** carpeta.</span><span class="sxs-lookup"><span data-stu-id="87786-349">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="87786-350">Este archivo debe incluir todos los registros cuya dirección sea 500.</span><span class="sxs-lookup"><span data-stu-id="87786-350">This should contain the all the records where the address is 500.</span></span>  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     <span data-ttu-id="87786-351">Estos datos de registro devuelto deben coincidir con los datos devueltos por la consulta en el sistema JD Edwards OneWorld en la práctica 1.</span><span class="sxs-lookup"><span data-stu-id="87786-351">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="87786-352">Al comparar los registros obtenidos en la práctica 1, podrá comprobar que el **obtener** método ha funcionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="87786-352">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="87786-353">Resumen</span><span class="sxs-lookup"><span data-stu-id="87786-353">Summary</span></span>  
 <span data-ttu-id="87786-354">En esta práctica, primero comprobó que los requisitos previos estaban correctamente configurados para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-354">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-355">A continuación, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk que contiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="87786-355">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="87786-356">Configuró la orquestación de BizTalk para usar el adaptador de JD Edwards OneWorld a fin de de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-356">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-357">Para configurar la orquestación, creó puertos de envío, recepción y envío/recepción.</span><span class="sxs-lookup"><span data-stu-id="87786-357">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="87786-358">Enlazó estos puertos al adaptador de JD Edwards OneWorld y asignó mensajes a los puertos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="87786-358">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="87786-359">Una vez completado el proyecto de BizTalk, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generarlo e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="87786-359">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="87786-360">A continuación, configuró la nueva aplicación y la ejecutó para obtener datos del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="87786-360">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="87786-361">Para comprobar que la aplicación funcionó correctamente, comparó el archivo XML de salida con el archivo que recibió del sistema JD Edwards OneWorld en la Práctica 1.</span><span class="sxs-lookup"><span data-stu-id="87786-361">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>