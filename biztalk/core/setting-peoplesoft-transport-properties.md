---
title: Establecer propiedades de transporte de PeopleSoft | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 44b5f015-59f1-43a3-9673-a5ba40266843
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ecfd221d28312e84dcbaf7d8c83abc4f5191f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-peoplesoft-transport-properties"></a><span data-ttu-id="c6af2-102">Definición de las propiedades de transporte de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6af2-102">Setting PeopleSoft Transport Properties</span></span>
<span data-ttu-id="c6af2-103">Las propiedades de transporte de PeopleSoft se usan en el diseño y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c6af2-103">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="c6af2-104">En el **propiedades de transporte** cuadro de diálogo, Establece los parámetros de conexión y credenciales específicas para el sistema de servidor y los objetos que está intentando obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="c6af2-104">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="c6af2-105">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="c6af2-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="c6af2-106">Expanda las propiedades necesarias del adaptador y complete toda la información que necesite para conectar con el servidor de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6af2-106">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="c6af2-107">Defina los parámetros de configuración para conectar el adaptador de Microsoft BizTalk para PeopleSoft Enterprise a PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c6af2-107">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="c6af2-108">Estos datos distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c6af2-108">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="c6af2-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c6af2-109">Parameter</span></span>|<span data-ttu-id="c6af2-110">Description</span><span class="sxs-lookup"><span data-stu-id="c6af2-110">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="c6af2-111">Cadena que representa el equipo y el puerto en que se ejecuta y escucha el servidor de aplicaciones de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6af2-111">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="c6af2-112">La sintaxis de la ruta de acceso de dirección URL para la aplicación PeopleSoft 8 es / / < nombre_equipo >:\<puerto >.</span><span class="sxs-lookup"><span data-stu-id="c6af2-112">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port>.</span></span> <span data-ttu-id="c6af2-113">Pida al administrador de PeopleSoft para el \<puerto > valor.</span><span class="sxs-lookup"><span data-stu-id="c6af2-113">Ask your PeopleSoft administrator for the \<port> value.</span></span> <span data-ttu-id="c6af2-114">El \<puerto > valor es el JOLT puerto de escucha de protocolo, no al puerto del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c6af2-114">The \<port> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="c6af2-115">El puerto JOLT predeterminado es 9000.</span><span class="sxs-lookup"><span data-stu-id="c6af2-115">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="c6af2-116">Establezca la variable JAVA_HOME para que apunte a la instalación de JDK, por ejemplo: **C:\j2sdk1.4.2_08**.</span><span class="sxs-lookup"><span data-stu-id="c6af2-116">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="c6af2-117">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.</span><span class="sxs-lookup"><span data-stu-id="c6af2-117">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="c6af2-118">Cadena que representa la contraseña del usuario para iniciar sesión en un sistema de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6af2-118">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="c6af2-119">Los caracteres no aparecen, pero están representados por asteriscos (*).</span><span class="sxs-lookup"><span data-stu-id="c6af2-119">The characters do not appear but are represented by asterisks (*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="c6af2-120">Para usar interfaces de componentes (solo para PeopleSoft 8), debe actualizar CLASSPATH para que incluya el archivo jar de la interfaz de componentes de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6af2-120">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="c6af2-121">Por ejemplo: **\web\PSJOA\psjoa.jar < PeopleSoft_Home >**.</span><span class="sxs-lookup"><span data-stu-id="c6af2-121">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="c6af2-122">Si no ha seleccionado **usar SSO**, debe establecer parámetros de credenciales para el adaptador de BizTalk para PeopleSoft Enterprise tener acceso al sistema de servidor.</span><span class="sxs-lookup"><span data-stu-id="c6af2-122">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="c6af2-123">Cadena que representa el nombre de usuario necesario para iniciar sesión en un sistema de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="c6af2-123">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="c6af2-124">Escriba un **parámetros adicionales** valor cuando se usa una fecha como una clave; tiene un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="c6af2-124">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="c6af2-125">AAAA-MM-DD es el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c6af2-125">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="c6af2-126">Escriba un **control de simultaneidad** valor que represente el número de llamadas, por ejemplo, 200, en **número máximo de llamadas simultáneas** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c6af2-126">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="c6af2-127">El **número máximo de llamadas simultáneas** parámetro activa una protección de sobrecarga si el servidor back-end no puede procesar la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="c6af2-127">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="c6af2-128">Una llamada concurrente es una solicitud para la que el adaptador todavía no tiene una respuesta.</span><span class="sxs-lookup"><span data-stu-id="c6af2-128">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="c6af2-129">Establecer **número máximo de llamadas simultáneas** en casos donde el rendimiento excede las capacidades de procesamiento de back-end.</span><span class="sxs-lookup"><span data-stu-id="c6af2-129">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="c6af2-130">El valor predeterminado de este campo es -1, lo que significa que no se produce ninguna protección.</span><span class="sxs-lookup"><span data-stu-id="c6af2-130">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="c6af2-131">Si BizTalk Server envía una solicitud al adaptador de transmisión y la cantidad de llamadas es igual a o supera el valor establecido para **número máximo de llamadas simultáneas**, el proceso de envío de la solicitud se guarda hasta que el de llamadas concurrentes número sea inferior al valor establecido.</span><span class="sxs-lookup"><span data-stu-id="c6af2-131">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6af2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6af2-132">See Also</span></span>  
 [<span data-ttu-id="c6af2-133">Crear controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="c6af2-133">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)