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
ms.openlocfilehash: 58e06eb1b606217aea6fe5e40ac645a2eaf623c2
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2017
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="05c13-102">Ejecutar una consulta de ejemplo de OneWorld JD Edwards</span><span class="sxs-lookup"><span data-stu-id="05c13-102">Execute a JD Edwards OneWorld Sample Query</span></span>
<span data-ttu-id="05c13-103">El adaptador de JD Edwards OneWorld permite obtener acceso al sistema JD Edwards OneWorld (JDEOW) desde un sistema [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c13-103">The JD Edwards OneWorld (JDEOW) system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="05c13-104">Este adaptador se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c13-104">This adapter is included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>
  
 <span data-ttu-id="05c13-105">Esta es la segunda parte del trabajo práctico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-105">This is the second part of the JD Edwards OneWorld lab work.</span></span> <span data-ttu-id="05c13-106">En la primera parte (Práctica 1), obtuvo acceso manualmente a los datos en el sistema JD Edwards OneWorld sin ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otra tecnología de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05c13-106">In the first part (Lab 1), you manually accessed data on the JD Edwards OneWorld system without the assistance of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or other Microsoft technologies.</span></span> <span data-ttu-id="05c13-107">En esta parte (Práctica 2), creará una orquestación de BizTalk como parte de un proyecto de BizTalk de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c13-107">In this part (Lab 2), you will create a BizTalk orchestration as part of a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project.</span></span> <span data-ttu-id="05c13-108">Configurará puertos en esta orquestación para usar el adaptador de JD Edwards OneWorld con el objetivo de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-108">You will configure ports on this orchestration to use the JD Edwards OneWorld adapter to get data from a JD Edwards OneWorld system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05c13-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05c13-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="05c13-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c13-110">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>
  
-   <span data-ttu-id="05c13-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c13-111">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]</span></span> 
  
-   <span data-ttu-id="05c13-112">Software JD Edwards OneWorld Client</span><span class="sxs-lookup"><span data-stu-id="05c13-112">JD Edwards OneWorld Client software</span></span>  
  
-   <span data-ttu-id="05c13-113">Conectividad de red para un sistema JD Edwards OneWorld en otro servidor</span><span class="sxs-lookup"><span data-stu-id="05c13-113">Network connectivity to a JD Edwards OneWorld system on another server</span></span>  
  
-   <span data-ttu-id="05c13-114">Adaptadores de Microsoft BizTalk para aplicaciones empresariales</span><span class="sxs-lookup"><span data-stu-id="05c13-114">Microsoft BizTalk Adapters for Enterprise Applications</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05c13-115">Vea [instalar y configurar los adaptadores para aplicaciones empresariales](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) para obtener información de configuración de la clave para los adaptadores de JD Edwards, PeopleSoft y TIBCO.</span><span class="sxs-lookup"><span data-stu-id="05c13-115">See [Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) for key configuration information for the JD Edwards, PeopleSoft, and TIBCO adapters.</span></span>  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a><span data-ttu-id="05c13-116">Práctica 2: ejecución de un consulta de ejemplo de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="05c13-116">Lab 2 - Executing a JD Edwards OneWorld Sample Query</span></span>  
 <span data-ttu-id="05c13-117">En esta práctica, ejecutará una **obtener** operación en el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-117">In this lab, you will execute a **Get** operation against the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-118">Específicamente, realizará las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="05c13-118">Specifically you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="05c13-119">Comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="05c13-119">Verify the JD Edwards OneWorld prerequisites</span></span>  
  
-   <span data-ttu-id="05c13-120">Configurar un puerto de envío de JD Edwards OneWorld en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05c13-120">Set up a JD Edwards OneWorld send port in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="05c13-121">Crear un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="05c13-121">Create a BizTalk orchestration project</span></span>  
  
-   <span data-ttu-id="05c13-122">Generar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="05c13-122">Build and deploy the project</span></span>  
  
-   <span data-ttu-id="05c13-123">Probar la aplicación y ver la salida XML</span><span class="sxs-lookup"><span data-stu-id="05c13-123">Test the application and view the XML output</span></span>  
  
 <span data-ttu-id="05c13-124">Usará el adaptador de JD Edwards OneWorld para obtener acceso a los datos del sistema JD Edwards OneWorld desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c13-124">You will use the JD Edwards OneWorld adapter to access data on the JD Edwards OneWorld system from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="05c13-125">Este adaptador le permite procesar objetos de JD Edwards OneWorld mediante solicitudes y respuestas ejecutadas por una orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-125">This adapter enables the processing of JD Edwards OneWorld objects by using requests and responses executed by an orchestration.</span></span> <span data-ttu-id="05c13-126">Se encuentran disponibles diversos métodos para objetos de esquema.</span><span class="sxs-lookup"><span data-stu-id="05c13-126">Many methods are available for a schema object.</span></span> <span data-ttu-id="05c13-127">Este laboratorio muestra cómo utilizar el **Address Book MBF** método.</span><span class="sxs-lookup"><span data-stu-id="05c13-127">This lab demonstrates how to use the **Address Book MBF** method.</span></span>  
  
 <span data-ttu-id="05c13-128">Antes de ejecutar una solicitud de servicio, debe crear esquemas de solicitud y respuesta de servicio para el objeto específico de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-128">Before running a service request, you must create service request and response schemas for the specific JD Edwards OneWorld object.</span></span> <span data-ttu-id="05c13-129">El Asistente para agregar elementos generados/agregar adaptador crea estos esquemas al interrogar directamente al objeto de metadatos de compatibilidad en JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-129">The Add Generated Items/Add Adapter Wizard creates these schemas by directly interrogating the supporting metadata object in JD Edwards OneWorld.</span></span> <span data-ttu-id="05c13-130">Esta práctica, describen los pasos necesarios para crear esquemas para la **Address Book MBF** método y procesar una consulta.</span><span class="sxs-lookup"><span data-stu-id="05c13-130">This lab illustrates the steps required to create schemas for the **Address Book MBF** method and to process a query.</span></span>  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a><span data-ttu-id="05c13-131">Paso 1: Comprobar los requisitos previos de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="05c13-131">Step 1: Verify the JD Edwards OneWorld prerequisites</span></span>  
 <span data-ttu-id="05c13-132">Antes de comenzar a crear un proyecto de BizTalk para usarlo con el adaptador de JD Edwards OneWorld, debe asegurarse de que los archivos y el adaptador están configurados correctamente para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-132">Before you start creating a BizTalk project for use with the JD Edwards OneWorld adapter, you need to be sure the files and the adapter are set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-133">En el equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el adaptador de JD Edwards OneWorld se comunica con el sistema JD Edwards OneWorld a través de la interfaz Java.</span><span class="sxs-lookup"><span data-stu-id="05c13-133">On the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer, the JD Edwards OneWorld adapter communicates with the JD Edwards OneWorld system by using the Java interface.</span></span>    

1. <span data-ttu-id="05c13-134">Cuatro archivos son necesarios para el acceso a la interfaz adecuada para un sistema JD Edwards OneWorld mediante el adaptador de JD Edwards OneWorld: Connector.jar, Kernel.jar, BTSLIBinterop.jar y JDEJAccess.jar.</span><span class="sxs-lookup"><span data-stu-id="05c13-134">Four files are necessary for proper interface access to a JD Edwards OneWorld system using the JD Edwards OneWorld adapter: Connector.jar, Kernel.jar, BTSLIBinterop.jar, and JDEJAccess.jar.</span></span>  
  
    -   <span data-ttu-id="05c13-135">Los archivos Connector.jar y Kernel.jar están incluidos en el sistema JD Edwards OneWorld y se obtienen desde un administrador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-135">The Connector.jar and Kernel.jar files come with the JD Edwards OneWorld system and are obtained from a JD Edwards OneWorld administrator.</span></span> <span data-ttu-id="05c13-136">Estos archivos se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="05c13-136">These files are located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="05c13-137">El sistema JD Edwards OneWorld genera el archivo BTSLIBinterop.jar al seguir las instrucciones incluidas en la Guía de instalación para adaptadores.</span><span class="sxs-lookup"><span data-stu-id="05c13-137">The BTSLIBinterop.jar file is generated by the JD Edwards OneWorld system by following the instructions included in the Installation Guide for the adapters.</span></span> <span data-ttu-id="05c13-138">Este archivo se encuentran en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="05c13-138">This file is located in the C:\JDEOWJars folder.</span></span>  
  
    -   <span data-ttu-id="05c13-139">El archivo JDEJAccess.jar forma parte del adaptador JDEOW y se incluye en la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="05c13-139">The JDEJAccess.jar file is a part of the JDEOW adapter and is included with the installation of the adapter.</span></span> <span data-ttu-id="05c13-140">De forma predeterminada, se encuentra en C:\Program Files\Microsoft BizTalk Adapters para Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="05c13-140">By default, it is located in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="05c13-141">Edwards OneWorld® \Classes carpeta.</span><span class="sxs-lookup"><span data-stu-id="05c13-141">Edwards OneWorld®\Classes folder.</span></span>  
  
2. <span data-ttu-id="05c13-142">Confirme la Connector.jar, Kernel.jar, y BTSLIBinterop.jar archivos existen en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en la carpeta C:\JDEOWJars.</span><span class="sxs-lookup"><span data-stu-id="05c13-142">Confirm the Connector.jar, Kernel.jar, and BTSLIBinterop.jar files exist on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\JDEOWJars folder.</span></span>  
  
3. <span data-ttu-id="05c13-143">Confirme que existe el archivo JDEJAccess.jar en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en el C:\Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.</span><span class="sxs-lookup"><span data-stu-id="05c13-143">Confirm the JDEJAccess.jar file exists on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer in the C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D.</span></span> <span data-ttu-id="05c13-144">Carpeta de Edwards OneWorld\Classes.</span><span class="sxs-lookup"><span data-stu-id="05c13-144">Edwards OneWorld\Classes folder.</span></span>  
  
## <a name="step-2-configure-biztalk-send-ports"></a><span data-ttu-id="05c13-145">Paso 2: Configurar puertos de envío de BizTalk</span><span class="sxs-lookup"><span data-stu-id="05c13-145">Step 2: Configure BizTalk send ports</span></span>  
<span data-ttu-id="05c13-146">A continuación, compruebe que el adaptador de JD Edwards OneWorld está instalado y crear el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="05c13-146">Next, verify that the JD Edwards OneWorld adapter is installed, and create the send port.</span></span>  

1.  <span data-ttu-id="05c13-147">Abra **administración de BizTalk Server**, expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, Expanda **configuración de plataforma**y, a continuación, expanda **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="05c13-147">Open **BizTalk Server Administration**, expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
    <span data-ttu-id="05c13-148">Confirmar la **JDE_OneWorld** adaptador aparece.</span><span class="sxs-lookup"><span data-stu-id="05c13-148">Confirm the **JDE_OneWorld** adapter is listed.</span></span> <span data-ttu-id="05c13-149">Si no está instalado el adaptador de JD Edwards OneWorld, instale los adaptadores de Microsoft BizTalk Adapters for Enterprise Applications (vea la sección anterior "Requisitos previos").</span><span class="sxs-lookup"><span data-stu-id="05c13-149">If the JD Edwards OneWorld adapter is not installed, install the BizTalk Adapters for Enterprise Applications (see the earlier "Prerequisites" section).</span></span> <span data-ttu-id="05c13-150">Una vez instalados los adaptadores, haga clic en **adaptadores** y, a continuación, haga clic en **nuevo - adaptador** para instalar el adaptador de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-150">After the adapters are installed, right-click **Adapters** and then click **New - Adapter** to install the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="05c13-151">Reinicie la instancia de host para que esto surta efecto.</span><span class="sxs-lookup"><span data-stu-id="05c13-151">Restart the host instance for this to take effect.</span></span>  
  
2. <span data-ttu-id="05c13-152">Expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1**.</span><span class="sxs-lookup"><span data-stu-id="05c13-152">Expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="05c13-153">Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**. Escriba los siguientes valores para estos campos:</span><span class="sxs-lookup"><span data-stu-id="05c13-153">Right-click **Send Ports**, click **New**, and then click **Static Solicit-Response Send Port**.Enter the following values for these fields:</span></span>  
  
    1.  <span data-ttu-id="05c13-154">**Nombre:**  `JDE_OneWorldPort`</span><span class="sxs-lookup"><span data-stu-id="05c13-154">**Name:**  `JDE_OneWorldPort`</span></span>  
  
    2.  <span data-ttu-id="05c13-155">**Tipo:**  `JDE_OneWorld`</span><span class="sxs-lookup"><span data-stu-id="05c13-155">**Type:**  `JDE_OneWorld`</span></span>  
  
    3.  <span data-ttu-id="05c13-156">**Controlador de envío:**  `BizTalkServerApplication`</span><span class="sxs-lookup"><span data-stu-id="05c13-156">**Send handler:**  `BizTalkServerApplication`</span></span>  
  
    4.  <span data-ttu-id="05c13-157">**Canalización de envío:**  `XMLTransmit`</span><span class="sxs-lookup"><span data-stu-id="05c13-157">**Send pipeline:**  `XMLTransmit`</span></span>  
  
    5.  <span data-ttu-id="05c13-158">**La canalización de recepción:**  `XMLReceive`</span><span class="sxs-lookup"><span data-stu-id="05c13-158">**Receive pipeline:**  `XMLReceive`</span></span>  
  
4.  <span data-ttu-id="05c13-159">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-159">Click **Configure**, and then enter the following property values:</span></span>  
  
    1.  <span data-ttu-id="05c13-160">**Host:** \<escriba su nombre de host JDEOW ></span><span class="sxs-lookup"><span data-stu-id="05c13-160">**Host:** \<enter your JDEOW host name></span></span>  
  
    2.  <span data-ttu-id="05c13-161">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="05c13-161">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
    3.  <span data-ttu-id="05c13-162">**Entorno JDEdwards:** \<entran en el entorno de JDEOW ></span><span class="sxs-lookup"><span data-stu-id="05c13-162">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
    4.  <span data-ttu-id="05c13-163">**Archivos JAR de JDEdwards:** \<escriba la ruta de acceso completa de archivos JAR ></span><span class="sxs-lookup"><span data-stu-id="05c13-163">**JDEdwards JAR files:** \<enter full path of JAR files></span></span>  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  <span data-ttu-id="05c13-164">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-164">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
    6.  <span data-ttu-id="05c13-165">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="05c13-165">**Port:**  `6009`</span></span>  
  
    7.  <span data-ttu-id="05c13-166">**Nombre de usuario:** \<escriba su nombre de usuario de JD Edwards ></span><span class="sxs-lookup"><span data-stu-id="05c13-166">**User Name:** \<enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
5.  <span data-ttu-id="05c13-167">Seleccione **Aceptar** para cerrar el **propiedades de puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="05c13-167">Select **OK** to close the **Send Port Properties**.</span></span>  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a><span data-ttu-id="05c13-168">Paso 3: Crear un proyecto de orquestación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="05c13-168">Step 3: Create a BizTalk Orchestration Project</span></span>  
<span data-ttu-id="05c13-169">A continuación, cree un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y configurar una orquestación en el proyecto para gestionar la comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-169">Next, create a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and configure an orchestration in the project to handle communication between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-170">Agregará puertos de recepción y envío, generará el proyecto y, a continuación, lo implementará.</span><span class="sxs-lookup"><span data-stu-id="05c13-170">You will add send and receive ports, build the project, and then deploy the project.</span></span>  

  
1.  <span data-ttu-id="05c13-171">Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]y cree un nuevo proyecto de BizTalk en la carpeta C:\LABS.</span><span class="sxs-lookup"><span data-stu-id="05c13-171">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], and create a new BizTalk project in the C:\LABS folder.</span></span> <span data-ttu-id="05c13-172">En el menú **Archivo** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="05c13-172">On the **File** menu, click **New**.</span></span> <span data-ttu-id="05c13-173">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="05c13-173">The **New Project** dialog box appears.</span></span> <span data-ttu-id="05c13-174">En la consola de administración de **Plantillas** , seleccione **Proyecto vacío de servidor BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="05c13-174">In the **Templates** section, select **Empty BizTalk Server project.**</span></span> <span data-ttu-id="05c13-175">Escriba `JDE_OW_Test` como nombre único del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-175">Enter `JDE_OW_Test` as the unique project name, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="05c13-176">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, haga clic en **Agregar**y, a continuación, en **Agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="05c13-176">In Solution Explorer, right-click the project, click **Add**, and then click **Add Generated Items**.</span></span> <span data-ttu-id="05c13-177">En el panel de categorías, seleccione **agregar metadatos de adaptador**, en el panel Plantillas, seleccione **agregar metadatos de adaptador**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-177">In the Categories pane, select **Add Adapter Metadata**, in the Templates pane, select **Add Adapter Metadata**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="05c13-178">En el Asistente para agregar adaptador, seleccione el **JD Edwards OneWorld** adaptador, seleccione el **JDE_OneWorldPort** puerto de envío que creó en el procedimiento anterior y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-178">In the Add Adapter Wizard, select the **JD Edwards OneWorld** adapter, select the **JDE_OneWorldPort** send port that you created in the preceding procedure, and then click **Next**.</span></span>  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  <span data-ttu-id="05c13-179">En el **seleccionar servicios para importar** página abierta **JD Edwards OneWorld**.</span><span class="sxs-lookup"><span data-stu-id="05c13-179">On the **Select Services to Import** page, open **JD Edwards OneWorld**.</span></span> <span data-ttu-id="05c13-180">La comunicación con el sistema JDEOW se establece a través del adaptador mediante el uso del programa BrowsingAgent.</span><span class="sxs-lookup"><span data-stu-id="05c13-180">The JDEOW system is contacted through the adapter by using the BrowsingAgent program.</span></span> <span data-ttu-id="05c13-181">El programa BrowsingAgent muestra los servicios que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="05c13-181">The BrowsingAgent returns the following services.</span></span>  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  <span data-ttu-id="05c13-182">Expanda **CALLBSFN** y desplácese hacia abajo hasta **N0100041 - Address Book MBF**.</span><span class="sxs-lookup"><span data-stu-id="05c13-182">Expand **CALLBSFN** and scroll down to **N0100041 - Address Book MBF**.</span></span> <span data-ttu-id="05c13-183">Seleccione N0100041 y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-183">Select N0100041 and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="05c13-184">En el Explorador de soluciones, hay una nueva orquestación de BizTalk con dos nuevos archivos de esquema asociados.</span><span class="sxs-lookup"><span data-stu-id="05c13-184">In Solution Explorer, there is a new BizTalk orchestration with two new associated schema files.</span></span> <span data-ttu-id="05c13-185">Estos archivos los crea el Asistente para agregar adaptador.</span><span class="sxs-lookup"><span data-stu-id="05c13-185">These files are created by the Add Adapter Wizard.</span></span> <span data-ttu-id="05c13-186">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-186">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 <span data-ttu-id="05c13-187">La orquestación acepta como entrada del adaptador de archivo un archivo XML con formato para el sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-187">This orchestration accepts as input from the File adapter an XML file formatted for the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-188">A su vez, usa el adaptador de JD Edwards OneWorld para enviar el archivo XML al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-188">The orchestration uses the JD Edwards OneWorld adapter to send the XML file to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-189">El sistema JD Edwards OneWorld procesa la consulta y genera un archivo XML de salida que contiene los resultados.</span><span class="sxs-lookup"><span data-stu-id="05c13-189">JD Edwards OneWorld processes the query and generates an output XML file containing the results.</span></span> <span data-ttu-id="05c13-190">Este archivo XML regresa a la orquestación mediante el adaptador de JD Edwards OneWorld y el adaptador de archivo escribe el archivo XML en la ubicación de salida del disco.</span><span class="sxs-lookup"><span data-stu-id="05c13-190">This XML file returns to the orchestration through the JD Edwards OneWorld adapter, and the File adapter writes the XML file to the output location on disk.</span></span>  
  
 <span data-ttu-id="05c13-191">Para completar la orquestación, debe crear y configurar puertos para recibir y enviar los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="05c13-191">To complete the orchestration, you need to create and configure ports to receive and send the XML files.</span></span> <span data-ttu-id="05c13-192">Primero, configure el puerto de recepción que usará el adaptador de archivo para introducir el archivo XML que contiene la consulta en la orquestación del disco.</span><span class="sxs-lookup"><span data-stu-id="05c13-192">First, configure a receive port to be used by the File adapter to input the XML containing the query into the orchestration from disk.</span></span>  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a><span data-ttu-id="05c13-193">Configurar un puerto de recepción para aceptar el archivo XML de entrada</span><span class="sxs-lookup"><span data-stu-id="05c13-193">Configure a receive port to accept the input XML file</span></span>  
  
1.  <span data-ttu-id="05c13-194">Haga doble clic en el archivo **BizTalk Orchestration.odx** para abrir la orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-194">Double-click the **BizTalk Orchestration.odx** file to open the orchestration.</span></span>  
  
2.  <span data-ttu-id="05c13-195">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="05c13-195">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="05c13-196">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="05c13-196">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="05c13-197">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-197">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="05c13-198">En el **propiedades de puerto** escriba `JDE_File_In` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-198">On the **Port Properties** page, enter `JDE_File_In` for **Name**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="05c13-199">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-199">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="05c13-200">**Nombre de tipo de puerto**:`JDE_FileIn_Port`</span><span class="sxs-lookup"><span data-stu-id="05c13-200">**Port Type Name**: `JDE_FileIn_Port`</span></span>  
  
     <span data-ttu-id="05c13-201">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="05c13-201">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="05c13-202">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="05c13-202">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
5.  <span data-ttu-id="05c13-203">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-203">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="05c13-204">**Dirección de puerto de comunicación**: **Siempre recibiré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="05c13-204">**Port direction of communication**: **I'll always be receiving messages on this port**</span></span>  
  
     <span data-ttu-id="05c13-205">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="05c13-205">**Port binding**: **Specify later**</span></span>  
  
6.  <span data-ttu-id="05c13-206">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-206">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="05c13-207">Por último, cree un puerto de envío/recepción para enviar al sistema JD Edwards OneWorld el archivo de entrada XML inicial que contiene la consulta.</span><span class="sxs-lookup"><span data-stu-id="05c13-207">Next, create a send/receive port to send the initial XML input file containing the query to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-208">Este puerto también recibirá un archivo XML de salida que contiene los resultados de la consulta correspondiente a la llamada realizada al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-208">This port will also receive an output XML file containing the query results from the call to the JD Edwards OneWorld system.</span></span>  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a><span data-ttu-id="05c13-209">Configurar un puerto de envío y recepción a la interfaz con JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="05c13-209">Configure a send/receive port to interface with JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="05c13-210">En el archivo BizTalk Orchestration.odx, haga clic en la superficie para puerto derecha y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="05c13-210">In the BizTalk Orchestration.odx file, right-click the right port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="05c13-211">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="05c13-211">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="05c13-212">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-212">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="05c13-213">En la página **Seleccione un tipo de puerto** , seleccione **Utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-213">On the **Select a Port Type** page, select **Use an existing Port Type**.</span></span> <span data-ttu-id="05c13-214">En **tipos de puertos disponibles**, seleccione **JD_OW_Test.N0100041**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-214">Under **Available Port Types**, select **JD_OW_Test.N0100041**,and then click **Next**.</span></span>  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  <span data-ttu-id="05c13-215">Seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-215">Select the following property values:</span></span>  
  
     <span data-ttu-id="05c13-216">**Dirección de puerto de comunicación**: **enviaré una solicitud y recibiré una respuesta**</span><span class="sxs-lookup"><span data-stu-id="05c13-216">**Port direction of communication**: **I'll be sending a request and receiving a response**</span></span>  
  
     <span data-ttu-id="05c13-217">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="05c13-217">**Port binding**: **Specify later**</span></span>  
  
4.  <span data-ttu-id="05c13-218">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-218">Click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="05c13-219">En la superficie del puerto, verá el puerto y los métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="05c13-219">On the port surface you will see the port and the available methods.</span></span>  
  
 <span data-ttu-id="05c13-220">Por último, configure el puerto de envío que usará el adaptador de archivo para enviar al disco el archivo XML que contiene los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="05c13-220">Finally, configure a send port to be used by the File adapter to output the XML containing the query results to disk.</span></span>  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a><span data-ttu-id="05c13-221">Configurar un puerto de envío para enviar el archivo XML en el disco</span><span class="sxs-lookup"><span data-stu-id="05c13-221">Configure a send port to output the XML file to disk</span></span>  
  
1.  <span data-ttu-id="05c13-222">En el archivo BizTalk Orchestration.odx, haga clic en la superficie de puerto de la izquierda y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="05c13-222">In the BizTalk Orchestration.odx file, right-click the left port surface and then click **New Configured Port**.</span></span> <span data-ttu-id="05c13-223">De esta forma, se inicia el Asistente para configuración de puertos.</span><span class="sxs-lookup"><span data-stu-id="05c13-223">This starts the Port Configuration Wizard.</span></span> <span data-ttu-id="05c13-224">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-224">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
2.  <span data-ttu-id="05c13-225">En el **propiedades de puerto** escriba `JDE_FileOut` para **nombre**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05c13-225">On the **Port Properties** page, enter `JDE_FileOut` for **Name**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="05c13-226">En la página **Seleccionar un tipo de puerto** , seleccione **Crear un nuevo tipo de puerto**y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-226">On the **Select a Port Type** page, select **Create a new Port Type**, and then enter or select the following property values:</span></span>  
  
     <span data-ttu-id="05c13-227">**Nombre de tipo de puerto**:`JDE_FileOut_Port`</span><span class="sxs-lookup"><span data-stu-id="05c13-227">**Port Type Name**: `JDE_FileOut_Port`</span></span>  
  
     <span data-ttu-id="05c13-228">**Patrón de comunicación**: **Unidireccional**</span><span class="sxs-lookup"><span data-stu-id="05c13-228">**Communication Pattern**: **One Way**</span></span>  
  
     <span data-ttu-id="05c13-229">**Restricciones de acceso**: **Interno: limitado a este proyecto**</span><span class="sxs-lookup"><span data-stu-id="05c13-229">**Access Restrictions**: **Internal - limited to this project**</span></span>  
  
4.  <span data-ttu-id="05c13-230">Haga clic en **Siguiente** para ir a la página **Enlace de puerto** y seleccione los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-230">Click **Next** to go to the **Port Binding** page, and then select the following property values:</span></span>  
  
     <span data-ttu-id="05c13-231">**Dirección de puerto de comunicación**: **Siempre enviaré los mensajes en este puerto**</span><span class="sxs-lookup"><span data-stu-id="05c13-231">**Port direction of communication**: **I'll always be sending messages on this port**</span></span>  
  
     <span data-ttu-id="05c13-232">**Enlace de puerto**: **Especificar más tarde**</span><span class="sxs-lookup"><span data-stu-id="05c13-232">**Port binding**: **Specify later**</span></span>  
  
5.  <span data-ttu-id="05c13-233">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-233">Click **Next**, and then click **Finish**.</span></span>  
  
 <span data-ttu-id="05c13-234">En la superficie del puerto se muestran los puertos nuevos y los métodos disponibles para los servicios JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-234">Displayed on the port surface are the new ports and the available methods for the JD Edwards OneWorld services.</span></span> <span data-ttu-id="05c13-235">Más adelante, especificará el adaptador de JD Edwards OneWorld para enviar y recibir archivos provenientes del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-235">Later you will specify the JD Edwards OneWorld adapter to send and receive files from the JD Edwards OneWorld system.</span></span>  
  
 <span data-ttu-id="05c13-236">El **JDE_File_In** y **JDE_File_Out** puertos que acaba de crear necesidad de tipos de mensajes asociados.</span><span class="sxs-lookup"><span data-stu-id="05c13-236">The **JDE_File_In** and **JDE_File_Out** ports you just created need associated message types.</span></span>  
  
#### <a name="assign-message-types-to-the-ports"></a><span data-ttu-id="05c13-237">Asignar a tipos de mensajes a los puertos</span><span class="sxs-lookup"><span data-stu-id="05c13-237">Assign message types to the ports</span></span>  
  
1.  <span data-ttu-id="05c13-238">En la superficie de puerto de la izquierda, en la **JDE_File_In** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-238">On the left port surface, on the **JDE_File_In** port, click **Request**.</span></span> <span data-ttu-id="05c13-239">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBF**.</span><span class="sxs-lookup"><span data-stu-id="05c13-239">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBF**.</span></span>  
  
2.  <span data-ttu-id="05c13-240">En la superficie de puerto de la izquierda, en la **JDE_File_Out** de puerto, haga clic en **solicitar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-240">On the left port surface, on the **JDE_File_Out** port, click **Request**.</span></span> <span data-ttu-id="05c13-241">En la ventana Propiedades, expanda **tipo de mensaje**, expanda **mensaje de varias partes**y, a continuación, haga clic en **JDE_OW_TestAddressBookMasterMBFResponse**.</span><span class="sxs-lookup"><span data-stu-id="05c13-241">In the Properties window, expand **Message Type**, expand **Multi-part Message**, and then click **JDE_OW_TestAddressBookMasterMBFResponse**.</span></span>  
  
 <span data-ttu-id="05c13-242">Inserte dos **enviar** y dos formas **recepción** formas en la orquestación para vincular a los puertos.</span><span class="sxs-lookup"><span data-stu-id="05c13-242">Insert two **Send** shapes and two **Receive** shapes into the orchestration to link to the ports.</span></span>  
  
#### <a name="add-send-and-receive-shapes"></a><span data-ttu-id="05c13-243">Agregar el envío y recepción formas</span><span class="sxs-lookup"><span data-stu-id="05c13-243">Add Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="05c13-244">Arrastre un componente **Recepción** desde el cuadro de herramientas y suéltelo inmediatamente debajo del inicio de la orquestación (el círculo verde).</span><span class="sxs-lookup"><span data-stu-id="05c13-244">Drag a **Receive** component from the Toolbox and drop it immediately below the start of the orchestration (the green circle).</span></span> <span data-ttu-id="05c13-245">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `Get_File` para el **nombre**y establezca **activar** a `true`.</span><span class="sxs-lookup"><span data-stu-id="05c13-245">Click the **Receive** shape, and in the Properties window, enter `Get_File` for the **Name**, and set **Activate** to `true`.</span></span> <span data-ttu-id="05c13-246">De este modo se activará la orquestación cuando se reciba un documento entrante en este puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="05c13-246">Doing so will activate the orchestration when an incoming document is received on this receive port.</span></span>  
  
2.  <span data-ttu-id="05c13-247">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **GetFileReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="05c13-247">Drag a **Send** component from the Toolbox and drop it immediately below the **GetFileReceive** shape.</span></span> <span data-ttu-id="05c13-248">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `SendToJDEOW` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="05c13-248">Click the new **Send** shape, and in the Properties window, enter `SendToJDEOW` for the **Name**.</span></span>  
  
3.  <span data-ttu-id="05c13-249">Arrastre un **recepción** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **SendToJDEOWSend** forma.</span><span class="sxs-lookup"><span data-stu-id="05c13-249">Drag a **Receive** component from the Toolbox and drop it immediately below the **SendToJDEOWSend** shape.</span></span> <span data-ttu-id="05c13-250">Haga clic en el **recepción** forma y, en la ventana Propiedades, escriba `JDEOW_Resp` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="05c13-250">Click the **Receive** shape, and in the Properties window, enter `JDEOW_Resp` for the **Name**.</span></span>  
  
4.  <span data-ttu-id="05c13-251">Arrastre un **enviar** componente del cuadro de herramientas y suéltelo inmediatamente debajo del **JDEOW_RespReceive** forma.</span><span class="sxs-lookup"><span data-stu-id="05c13-251">Drag a **Send** component from the Toolbox and drop it immediately below the **JDEOW_RespReceive** shape.</span></span> <span data-ttu-id="05c13-252">Haga clic en el nuevo **enviar** forma y, en la ventana Propiedades, escriba `FileToDisk` para el **nombre**.</span><span class="sxs-lookup"><span data-stu-id="05c13-252">Click the new **Send** shape, and in the Properties window, enter `FileToDisk` for the **Name**.</span></span>  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  <span data-ttu-id="05c13-253">Conectar el **JDE_FileIn** puerto a la **GetFileReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="05c13-253">Connect the **JDE_FileIn** port to the **GetFileReceive** component.</span></span>  
  
6.  <span data-ttu-id="05c13-254">Conectar el **JDE_FileOut** puerto a la **FileToDiskReceive** componente.</span><span class="sxs-lookup"><span data-stu-id="05c13-254">Connect the **JDE_FileOut** port to the **FileToDiskReceive** component.</span></span>  
  
7.  <span data-ttu-id="05c13-255">Vaya a **Vista orquestación** y expanda **mensajes**.</span><span class="sxs-lookup"><span data-stu-id="05c13-255">Go to **Orchestration View** and expand **Messages**.</span></span> <span data-ttu-id="05c13-256">Cambie el identificador para **Message_1** a `MsgToJDEOW`y para **Message_2** a`JDEOW_Resp.`</span><span class="sxs-lookup"><span data-stu-id="05c13-256">Change the identifier for **Message_1** to `MsgToJDEOW`, and for **Message_2** to `JDEOW_Resp.`</span></span>  
  
8.  <span data-ttu-id="05c13-257">Resalte el **SendToJDEOWSend** componente y establezca su **mensaje** propiedad **MsgToJDEOW**.</span><span class="sxs-lookup"><span data-stu-id="05c13-257">Highlight the **SendToJDEOWSend** component and set its **Message** property to **MsgToJDEOW**.</span></span>  
  
9. <span data-ttu-id="05c13-258">Resalte el **JDEOW_RespReceive** componente y establezca su **mensaje** propiedad **JDEOW_Resp**.</span><span class="sxs-lookup"><span data-stu-id="05c13-258">Highlight the **JDEOW_RespReceive** component and set its **Message** property to **JDEOW_Resp**.</span></span>  
  
10. <span data-ttu-id="05c13-259">Conectar **SendToJDEOW** a la **solicitar** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="05c13-259">Connect **SendToJDEOW** to the **Request** portion of the **JDE_OW_Port** port.</span></span>  
  
11. <span data-ttu-id="05c13-260">Conectar **JDEOW_Resp** a la **respuesta** parte de la **JDE_OW_Port** puerto.</span><span class="sxs-lookup"><span data-stu-id="05c13-260">Connect **JDEOW_Resp** to the **Response** portion of the **JDE_OW_Port** port.</span></span>  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
## <a name="step-4-build-and-deploy-the-project"></a><span data-ttu-id="05c13-261">Paso 4: Compilar e implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="05c13-261">Step 4: Build and deploy the project</span></span>  
 <span data-ttu-id="05c13-262">Ahora, el proyecto de BizTalk está completo y puede generarlo e implementarlo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05c13-262">Now the BizTalk project is complete and you can build and deploy it in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="05c13-263">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="05c13-263">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="05c13-264">Para generar el proyecto, es necesario un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="05c13-264">To build the project, you need a strong name key file.</span></span> <span data-ttu-id="05c13-265">En el símbolo del sistema, escriba lo siguiente para crear un archivo de clave de nombre seguro:</span><span class="sxs-lookup"><span data-stu-id="05c13-265">At the command prompt, enter the following to create a strong name key file:</span></span>  
  
     <span data-ttu-id="05c13-266">**sn -k labs.snk**</span><span class="sxs-lookup"><span data-stu-id="05c13-266">**sn -k labs.snk**</span></span>  
  
3.  <span data-ttu-id="05c13-267">En el Explorador de soluciones, haga clic en el **JD_OW_Test** del proyecto y, a continuación, haga clic en **propiedades** para iniciar el Diseñador de proyectos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="05c13-267">In Solution Explorer, right-click the **JD_OW_Test** project, and then click **Properties** to launch the Project Designer for the project.</span></span>  
  
4.  <span data-ttu-id="05c13-268">Haga clic en la pestaña **Firma** .</span><span class="sxs-lookup"><span data-stu-id="05c13-268">Click the **Signing** tab.</span></span>  
  
5.  <span data-ttu-id="05c13-269">Seleccione la opción **Firmar el ensamblado** , haga clic en la lista desplegable para la opción **Seleccione un archivo de clave de nombre seguro** y, a continuación, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-269">Select **Sign the assembly** option, click drop-down list for the **Choose a strong name key file** option, and then click **Browse**.</span></span>  
  
6.  <span data-ttu-id="05c13-270">Busque y seleccione el archivo de clave: **labs.snk**y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="05c13-270">Browse to select the key file: **labs.snk**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="05c13-271">Haga clic en la pestaña **Implementación** del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="05c13-271">Click **Deployment** tab in the Project Designer.</span></span>  
  
8.  <span data-ttu-id="05c13-272">Establecer el **nombre de la aplicación** a `JDE_OW_Test`.</span><span class="sxs-lookup"><span data-stu-id="05c13-272">Set the **Application Name** to `JDE_OW_Test`.</span></span>  
  
9. <span data-ttu-id="05c13-273">En el Explorador de soluciones, haga clic en el **JDE_OW_Test** del proyecto y, a continuación, haga clic en **compilar.**</span><span class="sxs-lookup"><span data-stu-id="05c13-273">In Solution Explorer, right-click the **JDE_OW_Test** project, and then click **Build.**</span></span>  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. <span data-ttu-id="05c13-274">Cuando la compilación finalice correctamente, haga clic en el **XX_JD Edwards OneWorldQuery** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-274">After the build completes successfully, right-click the **XX_JD Edwards OneWorldQuery** project, and then click **Deploy**.</span></span> <span data-ttu-id="05c13-275">En la ventana de salida, aparecerá:</span><span class="sxs-lookup"><span data-stu-id="05c13-275">In the output window the following output will be displayed:</span></span>  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a><span data-ttu-id="05c13-276">Paso 5: Probar la aplicación y ver el resultado XML</span><span class="sxs-lookup"><span data-stu-id="05c13-276">Step 5: Test the Application and Viewing the XML Output</span></span>  
 <span data-ttu-id="05c13-277">A continuación, probará la aplicación que acaba de crear e implementar.</span><span class="sxs-lookup"><span data-stu-id="05c13-277">Now you will test the application that you have created and deployed.</span></span> <span data-ttu-id="05c13-278">Creará el archivo XML que inicia el proceso de orquestación y, a continuación, configurará carpetas para recibir y enviar archivos XML en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05c13-278">You will create the XML file that starts the orchestration process, and then you will configure folders to receive and send XML files within the application.</span></span> <span data-ttu-id="05c13-279">Una vez que haya configurado la aplicación, la ejecutará y visualizará los archivos XML que devuelve la orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-279">After you have configured the application, you will run it and view the XML files that the orchestration returns.</span></span>  
  
#### <a name="generate-the-xml-file-for-the-query"></a><span data-ttu-id="05c13-280">Generar el archivo XML de la consulta</span><span class="sxs-lookup"><span data-stu-id="05c13-280">Generate the XML file for the query</span></span>  
  
1.  <span data-ttu-id="05c13-281">En el Explorador de soluciones, haga doble clic en **N0100041Service_N0100041.xsd** para abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="05c13-281">In Solution Explorer, double-click **N0100041Service_N0100041.xsd** to open the file.</span></span>  
  
2.  <span data-ttu-id="05c13-282">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="05c13-282">Right-click **N0100041Service_N0100041.xsd** and then click **Properties**.</span></span> <span data-ttu-id="05c13-283">Para **Nombre de archivo de instancia de salida** , escriba la siguiente ruta de acceso y nombre de archivo para el XML del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05c13-283">For the **Output Instance Filename** enter the following path and file name for the sample XML:</span></span>  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  <span data-ttu-id="05c13-284">Haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="05c13-284">Click **OK.**</span></span> <span data-ttu-id="05c13-285">En la ventana Propiedades, seleccione  **\<esquema >** y establecer **referencia raíz:** a `AddressBookMasterMBF`.</span><span class="sxs-lookup"><span data-stu-id="05c13-285">In the Properties window, select **\<Schema>** and set **Root Reference:** to `AddressBookMasterMBF`.</span></span> <span data-ttu-id="05c13-286">Esto hará que el XML generado sólo incluirá el **consulta** xml.</span><span class="sxs-lookup"><span data-stu-id="05c13-286">This will cause the generated XML to include only the **Query** xml.</span></span>  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  <span data-ttu-id="05c13-287">Haga clic en **N0100041Service_N0100041.xsd** y, a continuación, haga clic en **generar instancia**.</span><span class="sxs-lookup"><span data-stu-id="05c13-287">Right-click **N0100041Service_N0100041.xsd** and then click **Generate Instance**.</span></span> <span data-ttu-id="05c13-288">Esto genera el **Sample.xml** archivo.</span><span class="sxs-lookup"><span data-stu-id="05c13-288">This generates the **Sample.xml** file.</span></span> <span data-ttu-id="05c13-289">Este archivo se colocará en la ubicación de recepción como entrada del adaptador para iniciar el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-289">This file will be dropped in the receive location as input to the adapter to start the orchestration process.</span></span>  
  
#### <a name="configure-and-start-the-biztalk-application"></a><span data-ttu-id="05c13-290">Configurar e iniciar la aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="05c13-290">Configure and start the BizTalk application</span></span>  
  
1.  <span data-ttu-id="05c13-291">Configure carpetas para recibir los archivos entrantes y enviar los salientes.</span><span class="sxs-lookup"><span data-stu-id="05c13-291">Configure folders for receiving the incoming files and sending the outgoing files.</span></span> <span data-ttu-id="05c13-292">Vaya a **C:\LABS\JDE_OW_Test** y cree dos nuevas subcarpetas denominadas `FileIn` y `FileOut`.</span><span class="sxs-lookup"><span data-stu-id="05c13-292">Go to **C:\LABS\JDE_OW_Test** and create two new subfolders named `FileIn` and `FileOut`.</span></span>  
  
2.  <span data-ttu-id="05c13-293">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **raíz de consola**, expanda**administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="05c13-293">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,expand **Console Root**, expand**BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="05c13-294">Haga clic en **JDE_OW_Test**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-294">Right-click **JDE_OW_Test**, and then click **Configure**.</span></span>  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  <span data-ttu-id="05c13-295">Seleccione **Orchestration_1** y haga clic en el cuadro desplegable **Host** .</span><span class="sxs-lookup"><span data-stu-id="05c13-295">Select **Orchestration_1** and click the **Host** drop-down box.</span></span> <span data-ttu-id="05c13-296">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="05c13-296">Select **BizTalkServerApplication**.</span></span>  
  
5.  <span data-ttu-id="05c13-297">En **puertos de recepción**, haga clic en  **\<ninguno >**.</span><span class="sxs-lookup"><span data-stu-id="05c13-297">Under **Receive Ports**, click **\<None>**.</span></span> <span data-ttu-id="05c13-298">En la lista desplegable, seleccione **Nuevo puerto de recepción**.</span><span class="sxs-lookup"><span data-stu-id="05c13-298">In the drop-down list, select **New Receive Port**.</span></span>  
  
6.  <span data-ttu-id="05c13-299">Para **nombre**, tipo `JDE_FileIn_Port`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-299">For **Name**, type `JDE_FileIn_Port`, and then click **OK**.</span></span> <span data-ttu-id="05c13-300">Aparecerá un cuadro de mensaje que indica que debe designar una ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="05c13-300">A message box appears stating that you need to designate a receive location.</span></span> <span data-ttu-id="05c13-301">Haga clic en **Aceptar**y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="05c13-301">Click **OK**, and then click **New**.</span></span>  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  <span data-ttu-id="05c13-302">Escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-302">Type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="05c13-303">**Nombre**: JDE_`FileInLoc`</span><span class="sxs-lookup"><span data-stu-id="05c13-303">**Name**: JDE_`FileInLoc`</span></span>  
  
     <span data-ttu-id="05c13-304">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="05c13-304">**Type**: **File**</span></span>  
  
     <span data-ttu-id="05c13-305">**Controlador de recepción**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="05c13-305">**Receive Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="05c13-306">**Canalización de recepción**: **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="05c13-306">**Receive Pipeline**: **XMLReceive**</span></span>  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  <span data-ttu-id="05c13-307">Haga clic en **configurar**, tipo `C:\LABS\JDE_OW_Test\FileIn` para **carpeta recepción**y, a continuación, haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="05c13-307">Click **Configure**, type `C:\LABS\JDE_OW_Test\FileIn` for **Receive Folder**, and then click **OK** three times.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. <span data-ttu-id="05c13-308">Haga clic en  **\<ninguno >** para **JDE_OW_Port** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="05c13-308">Click **\<None>** for **JDE_OW_Port** in the drop-down list.</span></span>  
  
10. <span data-ttu-id="05c13-309">Seleccione **nuevo puerto de envío** y, a continuación, seleccione o escriba los valores para las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="05c13-309">Select **New Send Port** and then select or type the following values for the properties:</span></span>  
  
     <span data-ttu-id="05c13-310">**Nombre**:`JDE_OW_Port`</span><span class="sxs-lookup"><span data-stu-id="05c13-310">**Name**: `JDE_OW_Port`</span></span>  
  
     <span data-ttu-id="05c13-311">**Tipo de**: **JDE_OneWorld**</span><span class="sxs-lookup"><span data-stu-id="05c13-311">**Type**: **JDE_OneWorld**</span></span>  
  
     <span data-ttu-id="05c13-312">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="05c13-312">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="05c13-313">**Canalizaciones**: **XMLTransmit** y **XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="05c13-313">**Pipelines**: **XMLTransmit** and **XMLReceive**</span></span>  
  
11. <span data-ttu-id="05c13-314">Haga clic en **Configurar**y escriba los siguientes valores de propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-314">Click **Configure**, and then enter the following property values:</span></span>  
  
     <span data-ttu-id="05c13-315">**Host:** \<escriba su nombre de host JDEOW ></span><span class="sxs-lookup"><span data-stu-id="05c13-315">**Host:** \<enter your JDEOW host name></span></span>  
  
     <span data-ttu-id="05c13-316">**JAVA_HOME:**`C:\j2sdk1.4.2_08`</span><span class="sxs-lookup"><span data-stu-id="05c13-316">**JAVA_HOME:** `C:\j2sdk1.4.2_08`</span></span>  
  
     <span data-ttu-id="05c13-317">**Entorno JDEdwards:** \<entran en el entorno de JDEOW ></span><span class="sxs-lookup"><span data-stu-id="05c13-317">**JDEdwards Environment:** \<enter your JDEOW environment></span></span>  
  
     <span data-ttu-id="05c13-318">**Archivos JAR de JDEdwards:**<enter full path of JAR files></span><span class="sxs-lookup"><span data-stu-id="05c13-318">**JDEdwards JAR files:** <enter full path of JAR files></span></span>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     <span data-ttu-id="05c13-319">**Contraseña:** utilice la lista desplegable y, a continuación, escriba la contraseña de JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-319">**Password:** Use the drop-down list and then enter your JD Edwards OneWorld password.</span></span>  
  
     <span data-ttu-id="05c13-320">**Puerto:**  `6009`</span><span class="sxs-lookup"><span data-stu-id="05c13-320">**Port:**  `6009`</span></span>  
  
     <span data-ttu-id="05c13-321">**Nombre de usuario:**<enter your JD Edwards User Name></span><span class="sxs-lookup"><span data-stu-id="05c13-321">**User Name:** <enter your JD Edwards User Name></span></span>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. <span data-ttu-id="05c13-322">Haga clic en **Aceptar** dos veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="05c13-322">Click **OK** twice to close the dialog boxes.</span></span>  
  
13. <span data-ttu-id="05c13-323">En el Applicationwindow configurar, haga clic en  **\<ninguno >** para **JDE_FileOut** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="05c13-323">In the Configure Applicationwindow, click **\<None>** for **JDE_FileOut** in the drop-down list.</span></span>  
  
14. <span data-ttu-id="05c13-324">Seleccione **Nuevo puerto de envío** y escriba o seleccione los siguientes valores para las propiedades:</span><span class="sxs-lookup"><span data-stu-id="05c13-324">Select **New Send Port** and type or select the following values for the properties:</span></span>  
  
     <span data-ttu-id="05c13-325">**Nombre**:`FileOutPort`</span><span class="sxs-lookup"><span data-stu-id="05c13-325">**Name**: `FileOutPort`</span></span>  
  
     <span data-ttu-id="05c13-326">**Tipo**: **Archivo**</span><span class="sxs-lookup"><span data-stu-id="05c13-326">**Type**: **File**</span></span>  
  
     <span data-ttu-id="05c13-327">**Controlador de envío**: **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="05c13-327">**Send Handler**: **BizTalkServerApplication**</span></span>  
  
     <span data-ttu-id="05c13-328">**Canalización de envío**: **XMLTransmit**</span><span class="sxs-lookup"><span data-stu-id="05c13-328">**Send Pipeline**: **XMLTransmit**</span></span>  
  
15. <span data-ttu-id="05c13-329">Haga clic en **configurar** y tipo`C:\Labs\JDE_OW_Test\FileOut` para **carpeta de destino.**</span><span class="sxs-lookup"><span data-stu-id="05c13-329">Click **Configure** and type`C:\Labs\JDE_OW_Test\FileOut` for **Destination Folder.**</span></span> <span data-ttu-id="05c13-330">. Mantenga **%MessageID%.xml** en **Nombre de archivo** because this results in a unique file en each message.</span><span class="sxs-lookup"><span data-stu-id="05c13-330">Keep **%MessageID%.xml** for **File Name** because this results in a unique file for each message.</span></span>  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. <span data-ttu-id="05c13-331">Haga clic en **Aceptar** tres veces para cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="05c13-331">Click **OK** three times to close the dialog boxes.</span></span>  
  
17. <span data-ttu-id="05c13-332">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic con el **JDE_OW_Test** aplicación y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="05c13-332">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console,right-click the **JDE_OW_Test** application, and then click **Start**.</span></span>  
  
#### <a name="test-the-orchestration"></a><span data-ttu-id="05c13-333">Probar la orquestación</span><span class="sxs-lookup"><span data-stu-id="05c13-333">Test the orchestration</span></span>  
  
1.  <span data-ttu-id="05c13-334">En el **C:\Labs\JDE_OW_Test** directorio el **Sample.xml** archivo aparecerá como:</span><span class="sxs-lookup"><span data-stu-id="05c13-334">In the **C:\Labs\JDE_OW_Test** directory the **Sample.xml** file will appear as:</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  <span data-ttu-id="05c13-335">Editar la **Sample.xml** archivo para quitar todo excepto la **cActionCode** y **mnAddressBookNumber** elementos.</span><span class="sxs-lookup"><span data-stu-id="05c13-335">Edit the **Sample.xml** file to remove everything except the **cActionCode** and **mnAddressBookNumber** elements.</span></span>  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  <span data-ttu-id="05c13-336">Para el **cActionCode** elemento inserte la letra `i`.</span><span class="sxs-lookup"><span data-stu-id="05c13-336">For the **cActionCode** element insert the letter `i`.</span></span>  
  
4.  <span data-ttu-id="05c13-337">Para **mnAddressBookNumber** insertar el número `500`.</span><span class="sxs-lookup"><span data-stu-id="05c13-337">For **mnAddressBookNumber** insert the number `500`.</span></span>  
  
5.  <span data-ttu-id="05c13-338">Guarde los cambios y copie el archivo en el **C:\Labs\JDE_OW_Test\FileIn** carpeta.</span><span class="sxs-lookup"><span data-stu-id="05c13-338">Save the changes and copy the file to the **C:\Labs\JDE_OW_Test\FileIn** folder.</span></span> <span data-ttu-id="05c13-339">Se trata de la ubicación de recepción que inicia el proceso de orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-339">This is the receive location that starts the orchestration process.</span></span>  
  
6.  <span data-ttu-id="05c13-340">En unos segundos, debe aparecer un archivo XML en el **C:\Labs\JDE_OW_Test\FileOut** carpeta.</span><span class="sxs-lookup"><span data-stu-id="05c13-340">In a few seconds, an XML file should appear in the **C:\Labs\JDE_OW_Test\FileOut** folder.</span></span> <span data-ttu-id="05c13-341">Este archivo debe incluir todos los registros cuya dirección sea 500.</span><span class="sxs-lookup"><span data-stu-id="05c13-341">This should contain the all the records where the address is 500.</span></span>  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     <span data-ttu-id="05c13-342">Estos datos de registro devuelto deben coincidir con los datos devueltos por la consulta en el sistema JD Edwards OneWorld en la práctica 1.</span><span class="sxs-lookup"><span data-stu-id="05c13-342">This returned record data should match the data returned by the query against the JD Edwards OneWorld system in Lab 1.</span></span> <span data-ttu-id="05c13-343">Al comparar los registros obtenidos en la práctica 1, podrá comprobar que el **obtener** método ha funcionado correctamente.</span><span class="sxs-lookup"><span data-stu-id="05c13-343">By comparing the records you obtained in Lab 1, you can verify that the **Get** method worked properly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="05c13-344">Resumen</span><span class="sxs-lookup"><span data-stu-id="05c13-344">Summary</span></span>  
 <span data-ttu-id="05c13-345">En esta práctica, primero comprobó que los requisitos previos estaban correctamente configurados para obtener acceso al sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-345">In this lab, you first verified that the prerequisites were set up correctly to access the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-346">A continuación, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para crear un nuevo proyecto de BizTalk que contiene una orquestación.</span><span class="sxs-lookup"><span data-stu-id="05c13-346">Then you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to create a new BizTalk project containing an orchestration.</span></span> <span data-ttu-id="05c13-347">Configuró la orquestación de BizTalk para usar el adaptador de JD Edwards OneWorld a fin de de obtener datos de un sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-347">You configured the BizTalk orchestration to use the JD Edwards OneWorld adapter to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-348">Para configurar la orquestación, creó puertos de envío, recepción y envío/recepción.</span><span class="sxs-lookup"><span data-stu-id="05c13-348">To configure the orchestration, you created send, receive, and send/receive ports.</span></span> <span data-ttu-id="05c13-349">Enlazó estos puertos al adaptador de JD Edwards OneWorld y asignó mensajes a los puertos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="05c13-349">You bound these ports to the JD Edwards OneWorld adapter, and assigned messages to the appropriate ports.</span></span>  
  
 <span data-ttu-id="05c13-350">Una vez completado el proyecto de BizTalk, usó [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para generarlo e implementarlo.</span><span class="sxs-lookup"><span data-stu-id="05c13-350">After you completed the BizTalk project, you used [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to build and deploy it.</span></span> <span data-ttu-id="05c13-351">A continuación, configuró la nueva aplicación y la ejecutó para obtener datos del sistema JD Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="05c13-351">You then configured your new application and ran it to get data from the JD Edwards OneWorld system.</span></span> <span data-ttu-id="05c13-352">Para comprobar que la aplicación funcionó correctamente, comparó el archivo XML de salida con el archivo que recibió del sistema JD Edwards OneWorld en la Práctica 1.</span><span class="sxs-lookup"><span data-stu-id="05c13-352">To verify that the application worked correctly, you compared its output XML file to the file that you received from the JD Edwards OneWorld system in Lab 1.</span></span>