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
ms.openlocfilehash: e4e15310442d12c0b2604eb0d22b071ff6c57212
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="6c31f-102">Ejecutar una consulta de ejemplo de OneWorld JD Edwards</span><span class="sxs-lookup"><span data-stu-id="6c31f-102">Execute a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="6c31f-103">El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld (JDEOW) desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c31f-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="6c31f-104">Este adaptador se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c31f-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="6c31f-105">Esta es la segunda parte del trabajo práctico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="6c31f-106">En la primera parte (Práctica 1), obtuvo acceso manualmente a los datos en el sistema JD Edwards OneWorld sin ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otra tecnología de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c31f-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="6c31f-107">En esta parte (Práctica 2), creará una orquestación de BizTalk como parte de un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c31f-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="6c31f-108">Configurará puertos en esta orquestación para usar el adaptador de JD Edwards OneWorld con el objetivo de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6c31f-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6c31f-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="6c31f-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c31f-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="6c31f-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c31f-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="6c31f-112">Software JD Edwards OneWorld Client</span><span class="sxs-lookup"><span data-stu-id="6c31f-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="6c31f-113">Conectividad de red para un sistema JD Edwards OneWorld en otro servidor</span><span class="sxs-lookup"><span data-stu-id="6c31f-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="6c31f-114">Adaptadores de Microsoft BizTalk para aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="6c31f-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c31f-115">Vea [instalar y configurar los adaptadores para aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) para obtener información de configuración de la clave para los adaptadores de JD Edwards, PeopleSoft y TIBCO.</span><span class="sxs-lookup"><span data-stu-id="6c31f-115">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="6c31f-116">Práctica 2: ejecución de un consulta de ejemplo de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="6c31f-116">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="6c31f-117">En esta práctica, ejecutará una **obtener** operación en el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-117">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-118">Específicamente, realizará las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="6c31f-118">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6c31f-119">Comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="6c31f-119">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="6c31f-120">Configurar un puerto de envío de JD Edwards OneWorld en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c31f-120">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="6c31f-121">Crear un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6c31f-121">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="6c31f-122">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="6c31f-122">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="6c31f-123">Probar la aplicación y ver la salida XML</span><span class="sxs-lookup"><span data-stu-id="6c31f-123">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="6c31f-124">Usará el adaptador de JD Edwards OneWorld para obtener acceso a los datos del sistema JD Edwards OneWorld desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c31f-124">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6c31f-125">Este adaptador le permite procesar objetos de JD Edwards OneWorld mediante solicitudes y respuestas ejecutadas por una orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-125">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="6c31f-126">Se encuentran disponibles diversos métodos para objetos de esquema.</span><span class="sxs-lookup"><span data-stu-id="6c31f-126">Many methods are available for a schema object.</span></span> <span data-ttu-id="6c31f-127">Este laboratorio muestra cómo utilizar el **Address Book MBF** método.</span><span class="sxs-lookup"><span data-stu-id="6c31f-127">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="6c31f-128">Antes de ejecutar una solicitud de servicio, debe crear esquemas de solicitud y respuesta de servicio para el objeto específico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-128">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="6c31f-129">El Asistente para agregar elementos generados/agregar adaptador crea estos esquemas al interrogar directamente al objeto de metadatos de compatibilidad en JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-129">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="6c31f-130">Esta práctica, describen los pasos necesarios para crear esquemas para la **Address Book MBF** método y procesar una consulta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-130">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="6c31f-131">Paso 1: Comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="6c31f-131">Step 1: Verify the JD Edwards OneWorld prerequisites</span></span>  
 <span data-ttu-id="6c31f-132">Antes de comenzar a crear un proyecto de BizTalk para usarlo con el adaptador de JD Edwards OneWorld, debe asegurarse de que los archivos y el adaptador están configurados correctamente para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-132">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-133">En el equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el adaptador de JD Edwards OneWorld se comunica con el sistema JD Edwards OneWorld a través de la interfaz Java.</span><span class="sxs-lookup"><span data-stu-id="6c31f-133">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>    

1. <span data-ttu-id="6c31f-134">Cuatro archivos son necesarios para el acceso a la interfaz adecuada para un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld: Connector.jar, Kernel.jar, BTSLIBinterop.jar y JDEJAccess.jar.</span><span class="sxs-lookup"><span data-stu-id="6c31f-134">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
    -   <span data-ttu-id="6c31f-135">Los archivos Connector.jar y Kernel.jar están incluidos en el sistema JD Edwards OneWorld y se obtienen desde un administrador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-135">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="6c31f-136">Estos archivos se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="6c31f-136">These files are located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="6c31f-137">El sistema JD Edwards OneWorld genera el archivo BTSLIBinterop.jar al seguir las instrucciones incluidas en la Guía de instalación para adaptadores.</span><span class="sxs-lookup"><span data-stu-id="6c31f-137">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="6c31f-138">Este archivo se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="6c31f-138">This file is located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="6c31f-139">El archivo JDEJAccess.jar forma parte del adaptador JDEOW y se incluye en la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="6c31f-139">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="6c31f-140">De forma predeterminada, se encuentra en C:\Program Files\Microsoft BizTalk Adapters para Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="6c31f-140">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="6c31f-141">Edwards OneWorld® \Classes carpeta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-141">Edwards OneWorld®\Classes folder.</span></span>  
  
2. <span data-ttu-id="6c31f-142">Confirme la Connector.jar, Kernel.jar, y BTSLIBinterop.jar archivos existen en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="6c31f-142">Confirm the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
3. <span data-ttu-id="6c31f-143">Confirme que existe el archivo JDEJAccess.jar en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en el C:\Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="6c31f-143">Confirm the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="6c31f-144">Carpeta de Edwards OneWorld\Classes.</span><span class="sxs-lookup"><span data-stu-id="6c31f-144">Edwards OneWorld\Classes folder.</span></span>  
  
## <a name="step-2-configure-biztalk-send-ports"></a><span data-ttu-id="6c31f-145">Paso 2: Configurar puertos de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6c31f-145">Step 2: Configure BizTalk send ports</span></span>  
<span data-ttu-id="6c31f-146">A continuación, compruebe que el adaptador de JD Edwards OneWorld está instalado y crear el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="6c31f-146">Next, verify that the JD Edwards OneWorld adapter is installed, and create the send port.</span></span>  

1.  <span data-ttu-id="6c31f-147">Abra **administración de BizTalk Server**, expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, Expanda **configuración de plataforma**y, a continuación, expanda **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-147">Open **BizTalk Server Administration**, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
    <span data-ttu-id="6c31f-148">Confirmar la **JDE_OneWorld** adaptador aparece.</span><span class="sxs-lookup"><span data-stu-id="6c31f-148">Confirm the **JDE_OneWorld** adapter is listed.</span></span> <span data-ttu-id="6c31f-149">Si no está instalado el adaptador de JD Edwards OneWorld, instale los adaptadores de Microsoft BizTalk Adapters for Enterprise Applications (vea la sección anterior "Requisitos previos").</span><span class="sxs-lookup"><span data-stu-id="6c31f-149">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="6c31f-150">Una vez instalados los adaptadores, haga clic en **adaptadores** y, a continuación, haga clic en **nuevo - adaptador** para instalar el adaptador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-150">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="6c31f-151">Reinicie la instancia de host para que esto surta efecto.</span><span class="sxs-lookup"><span data-stu-id="6c31f-151">Restart the host instance for this to take effect.</span></span>  
  
2. <span data-ttu-id="6c31f-152">Expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-152">Expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="6c31f-153">Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**. Escriba los siguientes valores para estos campos:</span><span class="sxs-lookup"><span data-stu-id="6c31f-153">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="6c31f-154">**Nombre:**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="6c31f-154">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="6c31f-155">**Tipo:**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="6c31f-155">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="6c31f-156">**Controlador de envío:**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="6c31f-156">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="6c31f-157">**Canalización de envío:**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="6c31f-157">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="6c31f-158">**La canalización de recepción:**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="6c31f-158">**Receive pipeline:**  `XMLReceive`</span></span>  
  
4.  <span data-ttu-id="6c31f-159">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-159">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="6c31f-160">**Host:** \<escriba su nombre de host JDEOW\></span><span class="sxs-lookup"><span data-stu-id="6c31f-160">**Host:** \<enter your JDEOW host name\></span></span>  
  
    2.  <span data-ttu-id="6c31f-161">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="6c31f-161">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="6c31f-162">**Entorno JDEdwards:** \<entran en el entorno de JDEOW\></span><span class="sxs-lookup"><span data-stu-id="6c31f-162">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
    4.  <span data-ttu-id="6c31f-163">**Archivos JAR de JDEdwards:** \<escriba la ruta de acceso completa de archivos JAR\></span><span class="sxs-lookup"><span data-stu-id="6c31f-163">**JDEdwards JAR files:** \<enter full path of JAR files\></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="6c31f-164">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-164">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="6c31f-165">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="6c31f-165">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="6c31f-166">**Nombre de usuario:** \<escriba su nombre de usuario de JD Edwards\></span><span class="sxs-lookup"><span data-stu-id="6c31f-166">**User Name:** \<enter your JD Edwards User Name\></span></span>  
  
     <span data-ttu-id="6c31f-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span><span class="sxs-lookup"><span data-stu-id="6c31f-167">![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")</span></span>  
  
5.  <span data-ttu-id="6c31f-168">Seleccione **Aceptar** para cerrar el **propiedades de puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-168">Select **OK** to close the **Send Port Properties**.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="6c31f-169">Paso 3: Crear un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6c31f-169">Step 3: Create a BizTalk Orchestration Project</span></span>  
<span data-ttu-id="6c31f-170">A continuación, cree un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y configurar una orquestación en el proyecto para gestionar la comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-170">Next, create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-171">Agregará puertos de recepción y envío, generará el proyecto y, a continuación, lo implementará.</span><span class="sxs-lookup"><span data-stu-id="6c31f-171">You will add send and receive ports, build the project, and then deploy the project.</span></span>  

  
1.  <span data-ttu-id="6c31f-172">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y cree un nuevo proyecto de BizTalk en la carpeta C:\LABS.</span><span class="sxs-lookup"><span data-stu-id="6c31f-172">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="6c31f-173">En el menú **Archivo** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-173">On the **File** menu, click **New**.</span></span> <span data-ttu-id="6c31f-174">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="6c31f-174">The **New Project** dialog box appears.</span></span> <span data-ttu-id="6c31f-175">En la consola de administración de **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="6c31f-175">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="6c31f-176">Escriba `JDE_OW_Test` como nombre único del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-176">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="6c31f-177">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, haga clic en **Agregar**y, a continuación, en **Agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-177">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="6c31f-178">En el panel de categorías, seleccione **agregar metadatos de adaptador**, en el panel Plantillas, seleccione **agregar metadatos de adaptador**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-178">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="6c31f-179">En el Asistente para agregar adaptador, seleccione el **JD Edwards OneWorld** adaptador, seleccione el **JDE_OneWorldPort** puerto de envío que creó en el procedimiento anterior y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-179">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     <span data-ttu-id="6c31f-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span><span class="sxs-lookup"><span data-stu-id="6c31f-180">![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")</span></span>  
  
4.  <span data-ttu-id="6c31f-181">En el **seleccionar servicios para importar** página abierta **JD Edwards OneWorld**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-181">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="6c31f-182">La comunicación con el sistema JDEOW se establece a través del adaptador mediante el uso del programa BrowsingAgent.</span><span class="sxs-lookup"><span data-stu-id="6c31f-182">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="6c31f-183">El programa BrowsingAgent muestra los servicios que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-183">The BrowsingAgent returns the following services.</span></span>  
  
     <span data-ttu-id="6c31f-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="6c31f-184">![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")</span></span>  
  
5.  <span data-ttu-id="6c31f-185">Expanda **CALLBSFN** y desplácese hacia abajo hasta **N0100041 - Address Book MBF**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-185">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="6c31f-186">Seleccione N0100041 y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-186">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="6c31f-187">En el Explorador de soluciones, hay una nueva orquestación de BizTalk con dos nuevos archivos de esquema asociados.</span><span class="sxs-lookup"><span data-stu-id="6c31f-187">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="6c31f-188">Estos archivos los crea el Asistente para agregar adaptador.</span><span class="sxs-lookup"><span data-stu-id="6c31f-188">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="6c31f-189">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-189">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     <span data-ttu-id="6c31f-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span><span class="sxs-lookup"><span data-stu-id="6c31f-190">![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")</span></span>  
  
 <span data-ttu-id="6c31f-191">La orquestación acepta como entrada del adaptador de archivo un archivo XML con formato para el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-191">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-192">A su vez, usa el adaptador de JD Edwards OneWorld para enviar el archivo XML al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-192">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-193">El sistema JD Edwards OneWorld procesa la consulta y genera un archivo XML de salida que contiene los resultados.</span><span class="sxs-lookup"><span data-stu-id="6c31f-193">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="6c31f-194">Este archivo XML regresa a la orquestación mediante el adaptador de JD Edwards OneWorld y el adaptador de archivo escribe el archivo XML en la ubicación de salida del disco.</span><span class="sxs-lookup"><span data-stu-id="6c31f-194">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="6c31f-195">Para completar la orquestación, debe crear y configurar puertos para recibir y enviar los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="6c31f-195">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="6c31f-196">Primero, configure el puerto de recepción que usará el adaptador de archivo para introducir el archivo XML que contiene la consulta en la orquestación del disco.</span><span class="sxs-lookup"><span data-stu-id="6c31f-196">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="6c31f-197">Configurar un puerto de recepción para aceptar el archivo XML de entrada</span><span class="sxs-lookup"><span data-stu-id="6c31f-197">Configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="6c31f-198">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-198">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="6c31f-199">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-199">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="6c31f-200">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-200">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="6c31f-201">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-201">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="6c31f-202">En el **propiedades de puerto** escriba `JDE_File_In` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-202">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="6c31f-203">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-203">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-204">**Nombre de tipo de puerto**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="6c31f-204">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="6c31f-205">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="6c31f-205">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="6c31f-206">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="6c31f-206">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="6c31f-207">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-207">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-208">**Dirección de puerto de comunicación**: **Siempre recibiré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="6c31f-208">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="6c31f-209">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="6c31f-209">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="6c31f-210">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-210">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="6c31f-211">Por último, cree un puerto de envío/recepción para enviar al sistema JD Edwards OneWorld el archivo de entrada XML inicial que contiene la consulta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-211">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-212">Este puerto también recibirá un archivo XML de salida que contiene los resultados de la consulta correspondiente a la llamada realizada al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-212">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="6c31f-213">Configurar un puerto de envío y recepción a la interfaz con JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="6c31f-213">Configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="6c31f-214">En el archivo BizTalk Orchestration.odx, haga clic en la superficie para puerto derecha y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-214">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="6c31f-215">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-215">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="6c31f-216">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-216">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="6c31f-217">En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-217">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="6c31f-218">En **tipos de puertos disponibles**, seleccione **JD_OW_Test.N0100041**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-218">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     <span data-ttu-id="6c31f-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span><span class="sxs-lookup"><span data-stu-id="6c31f-219">![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")</span></span>  
  
3.  <span data-ttu-id="6c31f-220">Seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-220">Select the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-221">**Dirección de puerto de comunicación**: **enviaré una solicitud y recibiré una respuesta**</span><span class="sxs-lookup"><span data-stu-id="6c31f-221">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="6c31f-222">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="6c31f-222">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="6c31f-223">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-223">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="6c31f-224">En la superficie del puerto, verá el puerto y los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c31f-224">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="6c31f-225">Por último, configure el puerto de envío que usará el adaptador de archivo para enviar al disco el archivo XML que contiene los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-225">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="6c31f-226">Configurar un puerto de envío para enviar el archivo XML en el disco</span><span class="sxs-lookup"><span data-stu-id="6c31f-226">Configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="6c31f-227">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-227">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="6c31f-228">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-228">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="6c31f-229">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-229">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="6c31f-230">En el **propiedades de puerto** escriba `JDE_FileOut` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-230">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="6c31f-231">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-231">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-232">**Nombre de tipo de puerto**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="6c31f-232">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="6c31f-233">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="6c31f-233">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="6c31f-234">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="6c31f-234">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="6c31f-235">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-235">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-236">**Dirección de puerto de comunicación**: **Siempre enviaré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="6c31f-236">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="6c31f-237">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="6c31f-237">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="6c31f-238">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-238">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="6c31f-239">En la superficie del puerto se muestran los puertos nuevos y los métodos disponibles para los servicios JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-239">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="6c31f-240">Más adelante, especificará el adaptador de JD Edwards OneWorld para enviar y recibir archivos provenientes del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-240">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="6c31f-241">El **JDE_File_In** y **JDE_File_Out** puertos que acaba de crear necesidad de tipos de mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="6c31f-241">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
#### <a name="assign-message-types-to-the-ports"></a><span data-ttu-id="6c31f-242">Asignar a tipos de mensajes a los puertos</span><span class="sxs-lookup"><span data-stu-id="6c31f-242">Assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="6c31f-243">En la superficie de puerto de la izquierda, en la **JDE_File_In** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-243">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="6c31f-244">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBF**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-244">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="6c31f-245">En la superficie de puerto de la izquierda, en la **JDE_File_Out** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-245">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="6c31f-246">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBFResponse**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-246">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="6c31f-247">Inserte dos **enviar** y dos formas **recepción** formas en la orquestación para vincular a los puertos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-247">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="6c31f-248">Agregar el envío y recepción formas</span><span class="sxs-lookup"><span data-stu-id="6c31f-248">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="6c31f-249">Arrastre un componente **Recepción** desde el cuadro de herramientas y suéltelo inmediatamente debajo del inicio de la orquestación (el círculo verde).</span><span class="sxs-lookup"><span data-stu-id="6c31f-249">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="6c31f-250">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `Get_File` para el **nombre**y establezca **activar** a `true`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-250">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="6c31f-251">De este modo se activará la orquestación cuando se reciba un documento entrante en este puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="6c31f-251">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="6c31f-252">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **GetFileReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="6c31f-252">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="6c31f-253">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `SendToJDEOW` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-253">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="6c31f-254">Arrastre un **recepción** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **SendToJDEOWSend** forma.</span><span class="sxs-lookup"><span data-stu-id="6c31f-254">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="6c31f-255">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `JDEOW_Resp` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-255">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="6c31f-256">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **JDEOW_RespReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="6c31f-256">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="6c31f-257">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `FileToDisk` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-257">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     <span data-ttu-id="6c31f-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span><span class="sxs-lookup"><span data-stu-id="6c31f-258">![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")</span></span>  
  
5.  <span data-ttu-id="6c31f-259">Conectar el **JDE_FileIn** puerto a la **GetFileReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="6c31f-259">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="6c31f-260">Conectar el **JDE_FileOut** puerto a la **FileToDiskReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="6c31f-260">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="6c31f-261">Vaya a **Vista orquestación** y expanda **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-261">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="6c31f-262">Cambie el identificador para **Message_1** a `MsgToJDEOW`y para **Message_2** a`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="6c31f-262">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="6c31f-263">Resalte el **SendToJDEOWSend** componente y establezca su **mensaje** propiedad **MsgToJDEOW**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-263">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="6c31f-264">Resalte el **JDEOW_RespReceive** componente y establezca su **mensaje** propiedad **JDEOW_Resp**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-264">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="6c31f-265">Conectar **SendToJDEOW** a la **solicitar** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="6c31f-265">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="6c31f-266">Conectar **JDEOW_Resp** a la **respuesta** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="6c31f-266">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     <span data-ttu-id="6c31f-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span><span class="sxs-lookup"><span data-stu-id="6c31f-267">![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")</span></span>  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="6c31f-268">Paso 4: Compilar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="6c31f-268">Step 4: Build and deploy the project</span></span>  
 <span data-ttu-id="6c31f-269">Ahora, el proyecto de BizTalk está completo y puede generarlo e implementarlo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c31f-269">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="6c31f-270">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-270">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="6c31f-271">Para generar el proyecto, es necesario un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="6c31f-271">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="6c31f-272">En el símbolo del sistema, escriba lo siguiente para crear un archivo de clave de nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="6c31f-272">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="6c31f-273">**sn -k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="6c31f-273">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="6c31f-274">En el Explorador de soluciones, haga clic en el **JD_OW_Test** del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6c31f-274">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="6c31f-275">Haga clic en la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="6c31f-275">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="6c31f-276">Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-276">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="6c31f-277">Busque y seleccione el archivo de clave: **labs.snk**y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-277">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="6c31f-278">Haga clic en la pestaña **Implementación** del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-278">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="6c31f-279">Establecer el **nombre de la aplicación** a `JDE_OW_Test`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-279">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="6c31f-280">En el Explorador de soluciones, haga clic en el **JDE_OW_Test** del proyecto y, a continuación, haga clic en **compilar.**</span><span class="sxs-lookup"><span data-stu-id="6c31f-280">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     <span data-ttu-id="6c31f-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span><span class="sxs-lookup"><span data-stu-id="6c31f-281">![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")</span></span>  
  
10. <span data-ttu-id="6c31f-282">Cuando la compilación finalice correctamente, haga clic en el **XX_JD Edwards OneWorldQuery** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-282">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="6c31f-283">En la ventana de salida, aparecerá:</span><span class="sxs-lookup"><span data-stu-id="6c31f-283">In the output window the following output will be displayed:</span></span>  
  
     <span data-ttu-id="6c31f-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span><span class="sxs-lookup"><span data-stu-id="6c31f-284">![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")</span></span>  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="6c31f-285">Paso 5: Probar la aplicación y ver el resultado XML</span><span class="sxs-lookup"><span data-stu-id="6c31f-285">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="6c31f-286">A continuación, probará la aplicación que acaba de crear e implementar.</span><span class="sxs-lookup"><span data-stu-id="6c31f-286">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="6c31f-287">Creará el archivo XML que inicia el proceso de orquestación y, a continuación, configurará carpetas para recibir y enviar archivos XML en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-287">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="6c31f-288">Una vez que haya configurado la aplicación, la ejecutará y visualizará los archivos XML que devuelve la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-288">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="6c31f-289">Generar el archivo XML de la consulta</span><span class="sxs-lookup"><span data-stu-id="6c31f-289">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="6c31f-290">En el Explorador de soluciones, haga doble clic en **N0100041Service_N0100041.xsd** para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="6c31f-290">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="6c31f-291">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-291">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="6c31f-292">Para **Nombre de archivo de instancia de salida** , escriba la siguiente ruta de acceso y nombre de archivo para el XML del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c31f-292">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="6c31f-293">Haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="6c31f-293">Click **OK.**</span></span> <span data-ttu-id="6c31f-294">En la ventana Propiedades, seleccione  **\<esquema\>**  y establecer **referencia raíz:** a `AddressBookMasterMBF`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-294">In the Properties window, select **\<Schema\>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="6c31f-295">Esto hará que el XML generado sólo incluirá el **consulta** xml.</span><span class="sxs-lookup"><span data-stu-id="6c31f-295">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     <span data-ttu-id="6c31f-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span><span class="sxs-lookup"><span data-stu-id="6c31f-296">![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")</span></span>  
  
4.  <span data-ttu-id="6c31f-297">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-297">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="6c31f-298">Esto genera el **Sample.xml** archivo.</span><span class="sxs-lookup"><span data-stu-id="6c31f-298">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="6c31f-299">Este archivo se colocará en la ubicación de recepción como entrada del adaptador para iniciar el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-299">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="6c31f-300">Configurar e iniciar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6c31f-300">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="6c31f-301">Configure carpetas para recibir los archivos entrantes y enviar los salientes.</span><span class="sxs-lookup"><span data-stu-id="6c31f-301">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="6c31f-302">Vaya a **C:\LABS\JDE_OW_Test** y cree dos nuevas subcarpetas denominadas `FileIn` y `FileOut`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-302">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="6c31f-303">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda**administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-303">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="6c31f-304">Haga clic en **JDE_OW_Test**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-304">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="6c31f-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span><span class="sxs-lookup"><span data-stu-id="6c31f-305">![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")</span></span>  
  
4.  <span data-ttu-id="6c31f-306">Seleccione **Orchestration_1** y haga clic en el cuadro desplegable **Host** .</span><span class="sxs-lookup"><span data-stu-id="6c31f-306">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="6c31f-307">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-307">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="6c31f-308">En **puertos de recepción**, haga clic en  **\<ninguno\>**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-308">Under **Receive Ports**, click **\<None\>**.</span></span> <span data-ttu-id="6c31f-309">En la lista desplegable, seleccione **Nuevo puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-309">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="6c31f-310">Para **nombre**, tipo `JDE_FileIn_Port`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-310">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="6c31f-311">Aparecerá un cuadro de mensaje que indica que debe designar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="6c31f-311">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="6c31f-312">Haga clic en **Aceptar**y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-312">Click **OK**, and then click **New**.</span></span>  
  
     <span data-ttu-id="6c31f-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span><span class="sxs-lookup"><span data-stu-id="6c31f-313">![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")</span></span>  
  
7.  <span data-ttu-id="6c31f-314">Escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-314">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="6c31f-315">**Nombre**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="6c31f-315">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="6c31f-316">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="6c31f-316">**Type**: **File**</span></span>  
  
     <span data-ttu-id="6c31f-317">**Controlador de recepción**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="6c31f-317">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="6c31f-318">**Canalización de recepción**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="6c31f-318">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     <span data-ttu-id="6c31f-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span><span class="sxs-lookup"><span data-stu-id="6c31f-319">![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")</span></span>  
  
8.  <span data-ttu-id="6c31f-320">Haga clic en **configurar**, tipo `C:\LABS\JDE_OW_Test\FileIn` para **carpeta recepción**y, a continuación, haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="6c31f-320">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     <span data-ttu-id="6c31f-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span><span class="sxs-lookup"><span data-stu-id="6c31f-321">![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")</span></span>  
  
9. <span data-ttu-id="6c31f-322">Haga clic en  **\<ninguno\>**  para **JDE_OW_Port** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6c31f-322">Click **\<None\>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="6c31f-323">Seleccione **nuevo puerto de envío** y, a continuación, seleccione o escriba los valores para las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c31f-323">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="6c31f-324">**Nombre**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="6c31f-324">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="6c31f-325">**Tipo de**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="6c31f-325">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="6c31f-326">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="6c31f-326">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="6c31f-327">**Canalizaciones**: **XMLTransmit** y **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="6c31f-327">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="6c31f-328">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-328">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="6c31f-329">**Host:** \<escriba su nombre de host JDEOW\></span><span class="sxs-lookup"><span data-stu-id="6c31f-329">**Host:** \<enter your JDEOW host name\></span></span>  
  
     <span data-ttu-id="6c31f-330">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="6c31f-330">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="6c31f-331">**Entorno JDEdwards:** \<entran en el entorno de JDEOW\></span><span class="sxs-lookup"><span data-stu-id="6c31f-331">**JDEdwards Environment:** \<enter your JDEOW environment\></span></span>  
  
     <span data-ttu-id="6c31f-332">**Archivos JAR de JDEdwards:**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="6c31f-332">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="6c31f-333">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-333">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="6c31f-334">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="6c31f-334">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="6c31f-335">**Nombre de usuario:**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="6c31f-335">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     <span data-ttu-id="6c31f-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span><span class="sxs-lookup"><span data-stu-id="6c31f-336">![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")</span></span>  
  
12. <span data-ttu-id="6c31f-337">Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6c31f-337">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="6c31f-338">En el Applicationwindow configurar, haga clic en  **\<ninguno\>**  para **JDE_FileOut** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6c31f-338">In the Configure Applicationwindow, click **\<None\>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="6c31f-339">Seleccione **Nuevo puerto de envío** y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c31f-339">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="6c31f-340">**Nombre**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="6c31f-340">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="6c31f-341">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="6c31f-341">**Type**: **File**</span></span>  
  
     <span data-ttu-id="6c31f-342">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="6c31f-342">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="6c31f-343">**Canalización de envío**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="6c31f-343">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="6c31f-344">Haga clic en **configurar** y tipo`C:\Labs\JDE_OW_Test\FileOut` para **carpeta de destino.**</span><span class="sxs-lookup"><span data-stu-id="6c31f-344">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="6c31f-345">. Mantenga **%MessageID%.xml** en **Nombre de archivo** because this results in a unique file en each message.</span><span class="sxs-lookup"><span data-stu-id="6c31f-345">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     <span data-ttu-id="6c31f-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span><span class="sxs-lookup"><span data-stu-id="6c31f-346">![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")</span></span>  
  
16. <span data-ttu-id="6c31f-347">Haga clic en **Aceptar** tres veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6c31f-347">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="6c31f-348">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic con el **JDE_OW_Test** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6c31f-348">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="6c31f-349">Probar la orquestación</span><span class="sxs-lookup"><span data-stu-id="6c31f-349">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="6c31f-350">En el **C:\Labs\JDE_OW_Test** directorio el **Sample.xml** archivo aparecerá como:</span><span class="sxs-lookup"><span data-stu-id="6c31f-350">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     <span data-ttu-id="6c31f-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span><span class="sxs-lookup"><span data-stu-id="6c31f-351">![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")</span></span>  
  
2.  <span data-ttu-id="6c31f-352">Editar la **Sample.xml** archivo para quitar todo excepto la **cActionCode** y **mnAddressBookNumber** elementos.</span><span class="sxs-lookup"><span data-stu-id="6c31f-352">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     <span data-ttu-id="6c31f-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span><span class="sxs-lookup"><span data-stu-id="6c31f-353">![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")</span></span>  
  
3.  <span data-ttu-id="6c31f-354">Para el **cActionCode** elemento inserte la letra `i`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-354">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="6c31f-355">Para **mnAddressBookNumber** insertar el número `500`.</span><span class="sxs-lookup"><span data-stu-id="6c31f-355">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="6c31f-356">Guarde los cambios y copie el archivo en el **C:\Labs\JDE_OW_Test\FileIn** carpeta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-356">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="6c31f-357">Se trata de la ubicación de recepción que inicia el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-357">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="6c31f-358">En unos segundos, debe aparecer un archivo XML en el **C:\Labs\JDE_OW_Test\FileOut** carpeta.</span><span class="sxs-lookup"><span data-stu-id="6c31f-358">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="6c31f-359">Este archivo debe incluir todos los registros cuya dirección sea 500.</span><span class="sxs-lookup"><span data-stu-id="6c31f-359">This should contain the all the records where the address is 500.</span></span>  
  
     <span data-ttu-id="6c31f-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span><span class="sxs-lookup"><span data-stu-id="6c31f-360">![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")</span></span>  
  
     <span data-ttu-id="6c31f-361">Estos datos de registro devuelto deben coincidir con los datos devueltos por la consulta en el sistema JD Edwards OneWorld en la práctica 1.</span><span class="sxs-lookup"><span data-stu-id="6c31f-361">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="6c31f-362">Al comparar los registros obtenidos en la práctica 1, podrá comprobar que el **obtener** método ha funcionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c31f-362">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6c31f-363">Resumen</span><span class="sxs-lookup"><span data-stu-id="6c31f-363">Summary</span></span>  
 <span data-ttu-id="6c31f-364">En esta práctica, primero comprobó que los requisitos previos estaban correctamente configurados para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-364">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-365">A continuación, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk que contiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="6c31f-365">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="6c31f-366">Configuró la orquestación de BizTalk para usar el adaptador de JD Edwards OneWorld a fin de de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-366">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-367">Para configurar la orquestación, creó puertos de envío, recepción y envío/recepción.</span><span class="sxs-lookup"><span data-stu-id="6c31f-367">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="6c31f-368">Enlazó estos puertos al adaptador de JD Edwards OneWorld y asignó mensajes a los puertos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6c31f-368">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="6c31f-369">Una vez completado el proyecto de BizTalk, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generarlo e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="6c31f-369">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="6c31f-370">A continuación, configuró la nueva aplicación y la ejecutó para obtener datos del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="6c31f-370">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="6c31f-371">Para comprobar que la aplicación funcionó correctamente, comparó el archivo XML de salida con el archivo que recibió del sistema JD Edwards OneWorld en la Práctica 1.</span><span class="sxs-lookup"><span data-stu-id="6c31f-371">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>