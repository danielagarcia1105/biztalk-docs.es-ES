---
title: "Crear artefactos de envío de adaptador de TIBCO Rendezvous | Documentos de Microsoft"
description: "Crear un puerto de envío, configure las propiedades de transporte para enviar mensajes a TIBCO Rendezvous desde BizTalk"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad996c4f-e6ed-4582-a768-0cb1ad25b1d8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6d03885423582c2657c9cb624c63f26ce1c6f3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="create-tibco-rendezvous-send-handlers"></a><span data-ttu-id="0cfeb-103">Crear controladores de envío TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0cfeb-103">Create TIBCO Rendezvous Send Handlers</span></span>
<span data-ttu-id="0cfeb-104">Esta sección explica cómo crear un esquema para usar TIBCO Rendezvous en una orquestación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-104">This section explains how to create a schema to use TIBCO Rendezvous in a BizTalk Server orchestration.</span></span>  
  
## <a name="create-a-send-port"></a><span data-ttu-id="0cfeb-105">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="0cfeb-105">Create a send port</span></span>
  
1.  <span data-ttu-id="0cfeb-106">En **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-106">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="0cfeb-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="0cfeb-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfeb-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0cfeb-109">Escriba un nombre para el puerto de envío, por ejemplo, `SendToTIBCORV`.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-109">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="0cfeb-110">Desde el **tipo** lista desplegable, seleccione **TIBCO Rendezvous**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-110">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="0cfeb-111">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="0cfeb-112">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  <span data-ttu-id="0cfeb-113">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="0cfeb-114">Microsoft BizTalk Adapter para TIBCO Rendezvous requiere que seleccione XMLTransmit canalización de envío y la canalización XMLReceive de recepción.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-114">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit pipeline for send, and XMLReceive pipeline for receive.</span></span>
        
    6.  <span data-ttu-id="0cfeb-115">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-115">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="0cfeb-116">En el **propiedades de transporte de TIBCO Rendezvous** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cfeb-116">In the **TIBCO Rendezvous Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0cfeb-117">Especifique las propiedades.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-117">Enter the properties.</span></span>  
  
         <span data-ttu-id="0cfeb-118">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="0cfeb-119">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-119">In the list, select the SSO affiliate application you created to represent the TIBCO Rendezvous system.</span></span>  
  
    3.  <span data-ttu-id="0cfeb-120">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="0cfeb-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-121">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0cfeb-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-122">Click **OK**.</span></span>  

## <a name="set-the-transport-properties"></a><span data-ttu-id="0cfeb-123">Establecer las propiedades de transporte</span><span class="sxs-lookup"><span data-stu-id="0cfeb-123">Set the transport properties</span></span>
<span data-ttu-id="0cfeb-124">Las propiedades de transporte de TIBCO Rendezvous se usan para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-124">The TIBCO Rendezvous Transport property is used for run time.</span></span> <span data-ttu-id="0cfeb-125">En el **propiedades de transporte**, establezca los parámetros de conexión que identifican el dominio TIBCO Rendezvous donde desea publicar los mensajes generados.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-125">In the **Transport Properties**, you set the connection parameters that identify the TIBCO Rendezvous domain where you want to publish the generated messages.</span></span>  
  
 
1.  <span data-ttu-id="0cfeb-126">En el **propiedades de transporte de TIBCO Rendezvous** pantalla, expanda **propiedades de remitente certificado** y escriba la información siguiente.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-126">On the **TIBCO Rendezvous Transport Properties** screen, expand **Certified Sender Properties** and enter the following information.</span></span>  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |<span data-ttu-id="0cfeb-127">Use</span><span class="sxs-lookup"><span data-stu-id="0cfeb-127">Use this</span></span>|<span data-ttu-id="0cfeb-128">Para</span><span class="sxs-lookup"><span data-stu-id="0cfeb-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0cfeb-129">**Nombre del libro de contabilidad**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-129">**Ledger name**</span></span>|<span data-ttu-id="0cfeb-130">El valor predeterminado es en blanco.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-130">Default value is blank.</span></span> <span data-ttu-id="0cfeb-131">Nombre del archivo de contabilidad que se va a usar para la entrega de mensajes certificados persistentes.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-131">Ledger file name to use for persistent certified message delivery.</span></span> <span data-ttu-id="0cfeb-132">Use solo las unidades locales.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-132">Use local drives only.</span></span>|  
    |<span data-ttu-id="0cfeb-133">**Nombre reutilizable**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-133">**Reusable name**</span></span>|<span data-ttu-id="0cfeb-134">El valor predeterminado es en blanco.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-134">Default value is blank.</span></span> <span data-ttu-id="0cfeb-135">Nombre reutilizable correspondiente que se va a usar para la entrega de mensajes certificados.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-135">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="0cfeb-136">El nombre debe ser único entre todos los nombres de correspondientes de mensajes certificados en la red.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-136">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
2.  <span data-ttu-id="0cfeb-137">Expanda **credenciales** y escriba la siguiente información de conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-137">Expand **Credentials** and enter the following information for connection to the server.</span></span>  
  
    |<span data-ttu-id="0cfeb-138">Use</span><span class="sxs-lookup"><span data-stu-id="0cfeb-138">Use this</span></span>|<span data-ttu-id="0cfeb-139">Para</span><span class="sxs-lookup"><span data-stu-id="0cfeb-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0cfeb-140">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-140">**Password**</span></span>|<span data-ttu-id="0cfeb-141">El valor predeterminado es en blanco.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-141">Default value is blank.</span></span> <span data-ttu-id="0cfeb-142">Contraseña para iniciar sesión en un demonio TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-142">Password for login to a Tibco Rendezvous daemon.</span></span>|  
    |<span data-ttu-id="0cfeb-143">**Nombre de usuario.**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-143">**User name**</span></span>|<span data-ttu-id="0cfeb-144">El valor predeterminado es en blanco.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-144">Default value is blank.</span></span> <span data-ttu-id="0cfeb-145">Nombre de usuario para el demonio TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-145">User name for Tibco Rendezvous daemon.</span></span>|  
  
3.  <span data-ttu-id="0cfeb-146">Expanda **configuración General** y escriba la siguiente información de conexión al servidor TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-146">Expand **General Settings** and enter the following information for connection to the TIBCO Rendezvous server.</span></span>  
  
    |<span data-ttu-id="0cfeb-147">Use</span><span class="sxs-lookup"><span data-stu-id="0cfeb-147">Use this</span></span>|<span data-ttu-id="0cfeb-148">Para</span><span class="sxs-lookup"><span data-stu-id="0cfeb-148">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0cfeb-149">**Número de página de códigos**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-149">**Code Page Number**</span></span>|<span data-ttu-id="0cfeb-150">El valor predeterminado es 65001 (página de códigos para la codificación UTF-8).</span><span class="sxs-lookup"><span data-stu-id="0cfeb-150">Default value is 65001 (code page for UTF-8 encoding).</span></span> <span data-ttu-id="0cfeb-151">Ésta es la página de códigos que usa el SDK de TIBCO Rendezvous para la codificación de Cadena.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-151">This is the code page that the TIBCO Rendezvous SDK uses for String encoding.</span></span>|  
    |<span data-ttu-id="0cfeb-152">**Nombre de sujeto predeterminado**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-152">**Default Subject Name**</span></span>|<span data-ttu-id="0cfeb-153">Valor predeterminado está vacío.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-153">Default is empty.</span></span> <span data-ttu-id="0cfeb-154">El nombre del sujeto está establecido en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-154">The subject name is set in the orchestration.</span></span> <span data-ttu-id="0cfeb-155">Si se usa un puerto para un tipo de mensaje, se puede proporcionar un nombre de sujeto predeterminado y se pueden simplificar las orquestaciones quitando la necesidad de establecer la propiedad del nombre de sujeto.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-155">If a port is used for one message type, you can provide a default subject name, and you can simplify orchestrations by removing the need to set the Subject name property.</span></span>|  
    |<span data-ttu-id="0cfeb-156">**Habilitar lote de tiempo**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-156">**Enable Time Batch**</span></span>|<span data-ttu-id="0cfeb-157">El valor predeterminado es False.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-157">Default value is False.</span></span> <span data-ttu-id="0cfeb-158">Habilitar/Deshabilitar característica de lote de tiempo de TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-158">Enable/Disable TIBCO Rendezvous Time Batch feature.</span></span>|  
    |<span data-ttu-id="0cfeb-159">**Asignar tipos no compatibles a cadena**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-159">**Map Unsupported types to string**</span></span>|<span data-ttu-id="0cfeb-160">Valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-160">Default value is True.</span></span> <span data-ttu-id="0cfeb-161">Si es true, los tipos no compatibles se asignan a la cadena si es posible.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-161">If true, unsupported types are mapped to string if it is possible.</span></span> <span data-ttu-id="0cfeb-162">Si es False, se genera un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-162">If False, a run-time error is generated.</span></span>|  
    |<span data-ttu-id="0cfeb-163">**Ruta de acceso a los archivos binarios, como ensamblados de TIBCO Rendezvous**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-163">**Path to Binaries, such as TIBCO Rendezvous assemblies**</span></span>|<span data-ttu-id="0cfeb-164">Proporcione esta información si no está ya en la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-164">Provide this information if it is not already in the PATH environment variable.</span></span>|  
    |<span data-ttu-id="0cfeb-165">**Conservar orden**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-165">**Preserver Order**</span></span>|<span data-ttu-id="0cfeb-166">Valor predeterminado es True.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-166">Default value is True.</span></span> <span data-ttu-id="0cfeb-167">Habilita la lógica para enviar mensajes a TIBCO Rendezvous en el mismo orden en el que se han recibido de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-167">Enables logic to send messages to TIBCO Rendezvous in the same order they were received from BizTalk Server.</span></span> <span data-ttu-id="0cfeb-168">Este parámetro fuerza la publicación en el mismo orden, pero no significa que los suscriptores lo reciban en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-168">This parameter forces publishing in the same order; it does not mean that subscribers receive them in the same order.</span></span>|  
    |<span data-ttu-id="0cfeb-169">**Identificador de puerto de envío**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-169">**Send Port Identifier**</span></span>|<span data-ttu-id="0cfeb-170">Este identificador aparece en los mensajes de registro asociados a este puerto.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-170">This identifier appears in log messages associated with this port.</span></span> <span data-ttu-id="0cfeb-171">Se proporciona como una comodidad.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-171">It is provided as a convenience.</span></span>|  
  
4.  <span data-ttu-id="0cfeb-172">Expanda **transporte Rendezvous** y escriba la información de conexión al servidor TIBCO Rendezvous, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-172">Expand **Rendezvous Transport** and enter the information for connection to the TIBCO Rendezvous server, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0cfeb-173">Se deben establecer los parámetros de conexión para el adaptador de Microsoft BizTalk para TIBCO Rendezvous, para tener acceso a TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-173">You must set connection parameters for Microsoft BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous.</span></span>  
  
    |<span data-ttu-id="0cfeb-174">Use</span><span class="sxs-lookup"><span data-stu-id="0cfeb-174">Use this</span></span>|<span data-ttu-id="0cfeb-175">Para</span><span class="sxs-lookup"><span data-stu-id="0cfeb-175">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0cfeb-176">**Demonio**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-176">**Daemon**</span></span>|<span data-ttu-id="0cfeb-177">Valor predeterminado está vacío.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-177">Default is empty.</span></span><br /><br /> <span data-ttu-id="0cfeb-178">Parámetro del demonio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-178">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="0cfeb-179">**Red**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-179">**Network**</span></span>|<span data-ttu-id="0cfeb-180">Valor predeterminado está vacío.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-180">Default is empty.</span></span><br /><br /> <span data-ttu-id="0cfeb-181">Parámetro de red del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-181">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="0cfeb-182">**Servicio**</span><span class="sxs-lookup"><span data-stu-id="0cfeb-182">**Service**</span></span>|<span data-ttu-id="0cfeb-183">Valor predeterminado está vacío.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-183">Default is empty.</span></span><br /><br /> <span data-ttu-id="0cfeb-184">Parámetro de servicio del transporte de Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-184">Rendezvous Transport Service parameter.</span></span>|  
  
5.  <span data-ttu-id="0cfeb-185">Proporcione credenciales mediante el inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="0cfeb-185">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="0cfeb-186">Hay dos métodos que puede utilizar para tener acceso al sistema TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-186">There are two methods that you can use to access the TIBCO Rendezvous system.</span></span> <span data-ttu-id="0cfeb-187">Puede usar credenciales (parámetros de nombre de usuario y contraseña) o el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-187">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    1.  <span data-ttu-id="0cfeb-188">Seleccione **Sí** en el **usar SSO** usar Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-188">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0cfeb-189">Vea [seguridad](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) para obtener información acerca de cómo configurar SSO.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-189">See [Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) for information about how to set up SSO.</span></span>  
  
    2.  <span data-ttu-id="0cfeb-190">Seleccione una aplicación afiliada de la lista.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-190">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="0cfeb-191">Una aplicación afiliada, creada por la herramientas de Inicio de sesión único empresarial, representa una aplicación como TBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-191">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO Rendezvous.</span></span> <span data-ttu-id="0cfeb-192">El adaptador de Microsoft BizTalk para TIBCO Rendezvous usa las credenciales de un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-192">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the credentials of an application user.</span></span> <span data-ttu-id="0cfeb-193">Estas credenciales se recuperan de la base de datos de SSO del sistema de servidor para una aplicación afiliada determinada.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-193">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0cfeb-194">Para obtener información sobre cómo crear una aplicación afiliada, vea [crear aplicaciones afiliadas](../core/creating-affiliate-applications1.md).</span><span class="sxs-lookup"><span data-stu-id="0cfeb-194">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
6.  <span data-ttu-id="0cfeb-195">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** después de proporcionar toda la información necesaria para aceptar la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-195">Click **Apply**, and then click **OK** after providing all required information to accept the connection information.</span></span>  
  
     <span data-ttu-id="0cfeb-196">Debe establecer parámetros de conexión para el adaptador de BizTalk para TIBCO Rendezvous tener acceso a TIBCO Rendezvous.</span><span class="sxs-lookup"><span data-stu-id="0cfeb-196">You must set connection parameters for BizTalk Adapter for TIBCO Rendezvous to access TIBCO Rendezvous .</span></span>  


## <a name="next-steps"></a><span data-ttu-id="0cfeb-197">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0cfeb-197">Next steps</span></span>
  
-   [<span data-ttu-id="0cfeb-198">Uso de puertos de envío de TIBCO Rendezvous desde BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0cfeb-198">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>](../core/using-tibco-rendezvous-send-ports-from-biztalk-server.md)  
  
-   [<span data-ttu-id="0cfeb-199">Asignación de tipos de datos para controladores de envío de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0cfeb-199">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="0cfeb-200">Propiedades de contexto de mensaje de BizTalk Server (Controladores de envío)</span><span class="sxs-lookup"><span data-stu-id="0cfeb-200">BizTalk Server Message Context Properties (Send Handlers)</span></span>](../core/biztalk-server-message-context-properties-send-handlers.md)