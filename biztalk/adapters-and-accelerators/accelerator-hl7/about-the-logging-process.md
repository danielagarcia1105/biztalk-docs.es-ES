---
title: Acerca del proceso de registro | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110c7d4505e6518836fa481ed268771aef72d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981061"
---
# <a name="about-the-logging-process"></a><span data-ttu-id="1e06d-102">Acerca del proceso de registro</span><span class="sxs-lookup"><span data-stu-id="1e06d-102">About the Logging Process</span></span>
<span data-ttu-id="1e06d-103">Puesto que las aplicaciones controlan críticos, tiempo datos confidenciales y monetario, la auditoría se convierte en una parte fundamental de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e06d-103">Since your applications handle critical, time sensitive and monetary data, auditing becomes a critical part of the application.</span></span> <span data-ttu-id="1e06d-104">Para habilitar la capacidad de administración de nivel de empresa y la disponibilidad, Microsoft [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se basa en el siguiente tiempo de ejecución compartido y los componentes administrativos:</span><span class="sxs-lookup"><span data-stu-id="1e06d-104">To enable enterprise level manageability and availability, Microsoft [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] relies on the following shared run time and administrative components:</span></span>  
  
- <span data-ttu-id="1e06d-105">**Registro**: recopilar y enviar todos los eventos de registro de forma administrada a una base de datos designada</span><span class="sxs-lookup"><span data-stu-id="1e06d-105">**Logging**: to collect and route all log events in a managed way to a designated database</span></span>  
  
- <span data-ttu-id="1e06d-106">**Supervisión de eventos y la depuración del servicio**: para configurar el comportamiento del registro y para investigar y administrar la información recopilada para los administradores del sistema y otros profesionales de TI</span><span class="sxs-lookup"><span data-stu-id="1e06d-106">**Event Monitoring and Service Debugging**: to configure logging behavior and to investigate/manage collected information for system administrators and other IT professionals</span></span>  
  
  <span data-ttu-id="1e06d-107">Con una mejora las características de auditoría de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], puede optimizar la eficacia operativa, seguridad y rendimiento para garantizar el cumplimiento con las normas de HL7.</span><span class="sxs-lookup"><span data-stu-id="1e06d-107">With the enhanced auditing features in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], you can optimize your operational efficiency, security, and performance to ensure compliance with HL7 regulations.</span></span>  
  
## <a name="types-of-data"></a><span data-ttu-id="1e06d-108">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1e06d-108">Types of Data</span></span>  
 <span data-ttu-id="1e06d-109">En este tema se describe los distintos tipos de datos de registro utilizados por la característica de registro y que se almacenan estos datos:</span><span class="sxs-lookup"><span data-stu-id="1e06d-109">This topic describes different types of logging data used by the logging feature and where this data is stored:</span></span>  
  
- <span data-ttu-id="1e06d-110">Datos de configuración: registro de los datos de configuración se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) e incluye datos de auditoría y la información de auditoría de SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Visor de eventos WMI de base de datos centralizada) ubicación.</span><span class="sxs-lookup"><span data-stu-id="1e06d-110">Configuration data: Logging configuration data is stored in the Configuration database (also known as the BizTalk Management database) and includes SQL auditing information and audit data ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event viewer, centralized database WMI) location.</span></span>  
  
- <span data-ttu-id="1e06d-111">Los datos de archivo: registro de eventos de la tabla en el registro de SQL almacena los datos de 'Registro'.</span><span class="sxs-lookup"><span data-stu-id="1e06d-111">Archival data: The EventLog table in the SQL log stores the 'Logging' data.</span></span>  
  
## <a name="how-logging-works"></a><span data-ttu-id="1e06d-112">Cómo funciona el registro</span><span class="sxs-lookup"><span data-stu-id="1e06d-112">How Logging Works</span></span>  
 <span data-ttu-id="1e06d-113">En este tema se describe los tres tipos de eventos que registra el software, así como las tres ubicaciones donde puede almacenar los datos registrados.</span><span class="sxs-lookup"><span data-stu-id="1e06d-113">This topic describes the three types of events the software logs, as well as the three locations where you can store the logged data.</span></span>  
  
|<span data-ttu-id="1e06d-114">Componente</span><span class="sxs-lookup"><span data-stu-id="1e06d-114">Component</span></span>|<span data-ttu-id="1e06d-115">Finalidad</span><span class="sxs-lookup"><span data-stu-id="1e06d-115">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="1e06d-116">Editor de configuración</span><span class="sxs-lookup"><span data-stu-id="1e06d-116">Configuration Editor</span></span>|<span data-ttu-id="1e06d-117">Para especificar dónde guardar los datos de registro.</span><span class="sxs-lookup"><span data-stu-id="1e06d-117">To specify where to save the log data.</span></span> <span data-ttu-id="1e06d-118">BTAHL7 admite el registro a cualquier combinación de las siguientes acciones: registro del Visor de eventos, WMI y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1e06d-118">BTAHL7 supports logging to any combination of the following: Event Viewer, WMI, and SQL Server logging.</span></span>|  
|<span data-ttu-id="1e06d-119">Agente de eventos</span><span class="sxs-lookup"><span data-stu-id="1e06d-119">Event Broker</span></span>|<span data-ttu-id="1e06d-120">Para recibir el registro de eventos producidos por otros componentes y los registre en función de registro de los datos de configuración.</span><span class="sxs-lookup"><span data-stu-id="1e06d-120">To receive log events raised by other components and log them based on logging configuration data.</span></span>|  
|<span data-ttu-id="1e06d-121">API de registro</span><span class="sxs-lookup"><span data-stu-id="1e06d-121">Logging API</span></span>|<span data-ttu-id="1e06d-122">Interfaz de registro que se llama a todos los ensamblados de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="1e06d-122">Logging interface called by all BTAHL7 assemblies.</span></span>|  
  
### <a name="types-of-logging"></a><span data-ttu-id="1e06d-123">Tipos de registro</span><span class="sxs-lookup"><span data-stu-id="1e06d-123">Types of Logging</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1e06d-124"> registra los tres tipos de errores:</span><span class="sxs-lookup"><span data-stu-id="1e06d-124"> logs three types of errors:</span></span>  
  
- <span data-ttu-id="1e06d-125">Error en un servicio iniciado o detenido, un evento o eventos informativos.</span><span class="sxs-lookup"><span data-stu-id="1e06d-125">Informational events, such a service started or stopped or an event failed.</span></span>  
  
- <span data-ttu-id="1e06d-126">Eventos de advertencia como errores no críticos y advertencias en [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] los registros de eventos.</span><span class="sxs-lookup"><span data-stu-id="1e06d-126">Warning events such as non-critical errors and warnings in [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Event logs.</span></span> <span data-ttu-id="1e06d-127">Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a un error de validación de datos.</span><span class="sxs-lookup"><span data-stu-id="1e06d-127">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because data validation failed.</span></span>  
  
- <span data-ttu-id="1e06d-128">Eventos de error para errores críticos en un componente.</span><span class="sxs-lookup"><span data-stu-id="1e06d-128">Error events for critical failures in a component.</span></span> <span data-ttu-id="1e06d-129">Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a errores del analizador.</span><span class="sxs-lookup"><span data-stu-id="1e06d-129">For example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspends a message because of parser failures.</span></span>  
  
  <span data-ttu-id="1e06d-130">Puede iniciar el sistema [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] eventos en las siguientes ubicaciones configurables:</span><span class="sxs-lookup"><span data-stu-id="1e06d-130">The system can log [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] events into following configurable locations:</span></span>  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]<span data-ttu-id="1e06d-131"> Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="1e06d-131"> Event viewer</span></span>  
  
- <span data-ttu-id="1e06d-132">Eventos de WMI</span><span class="sxs-lookup"><span data-stu-id="1e06d-132">WMI events</span></span>  
  
- <span data-ttu-id="1e06d-133">Base de datos centralizada (registro de SQL database)</span><span class="sxs-lookup"><span data-stu-id="1e06d-133">Centralized database (SQL logging database)</span></span>  
  
  <span data-ttu-id="1e06d-134">Un agente de eventos recibe todos los [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registro de eventos y, en función de la información de configuración, envía a la ubicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="1e06d-134">An event broker receives all [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging events and, based on the configuration information, sends them to the appropriate location.</span></span>  
  
### <a name="overview-of-features"></a><span data-ttu-id="1e06d-135">Información general de características</span><span class="sxs-lookup"><span data-stu-id="1e06d-135">Overview of Features</span></span>  
 <span data-ttu-id="1e06d-136">El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona la característica de registro:</span><span class="sxs-lookup"><span data-stu-id="1e06d-136">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logging feature provides:</span></span>  
  
-   <span data-ttu-id="1e06d-137">Una manera unificada de inicio de sesión de todos los mensajes de error</span><span class="sxs-lookup"><span data-stu-id="1e06d-137">A unified way of logging all the error messages</span></span>  
  
-   <span data-ttu-id="1e06d-138">Un repositorio centralizado para almacenar todos los detalles del evento</span><span class="sxs-lookup"><span data-stu-id="1e06d-138">A centralized repository for storing all event details</span></span>  
  
-   <span data-ttu-id="1e06d-139">Un modelo de objetos coherente para registrar mensajes que fluyen a las aplicaciones de línea de negocio discretas</span><span class="sxs-lookup"><span data-stu-id="1e06d-139">A consistent object model for logging messages flowing to discrete line-of-business applications</span></span>  
  
-   <span data-ttu-id="1e06d-140">Una combinación de registro y seguimiento para correlacionan los administradores del sistema de ayuda se ha registrado errores con documentos</span><span class="sxs-lookup"><span data-stu-id="1e06d-140">A combination of logging and tracing to help system administrators correlate logged errors with documents</span></span>  
  
## <a name="event-log-data"></a><span data-ttu-id="1e06d-141">Datos de registro de eventos</span><span class="sxs-lookup"><span data-stu-id="1e06d-141">Event Log Data</span></span>  
 <span data-ttu-id="1e06d-142">Este tema describe el formato y contenido de los datos de registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="1e06d-142">This topic describes the format and content of the event log data.</span></span>  
  
 <span data-ttu-id="1e06d-143">La siguiente tabla muestra los datos registrados típicos para partners.</span><span class="sxs-lookup"><span data-stu-id="1e06d-143">The following table shows typical logged data for partners.</span></span>  
  
|<span data-ttu-id="1e06d-144">data</span><span class="sxs-lookup"><span data-stu-id="1e06d-144">Data</span></span>|<span data-ttu-id="1e06d-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e06d-145">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e06d-146">LogData</span><span class="sxs-lookup"><span data-stu-id="1e06d-146">LogData</span></span>|<span data-ttu-id="1e06d-147">Registro de datos</span><span class="sxs-lookup"><span data-stu-id="1e06d-147">Data log</span></span>|  
|<span data-ttu-id="1e06d-148">NúmeroDeCategoría</span><span class="sxs-lookup"><span data-stu-id="1e06d-148">CategoryNumber</span></span>|<span data-ttu-id="1e06d-149">Número de categoría</span><span class="sxs-lookup"><span data-stu-id="1e06d-149">Category number</span></span>|  
|<span data-ttu-id="1e06d-150">EntryType</span><span class="sxs-lookup"><span data-stu-id="1e06d-150">EntryType</span></span>|<span data-ttu-id="1e06d-151">Tipo del evento</span><span class="sxs-lookup"><span data-stu-id="1e06d-151">Type of the event</span></span>|  
|<span data-ttu-id="1e06d-152">EventId</span><span class="sxs-lookup"><span data-stu-id="1e06d-152">EventId</span></span>|<span data-ttu-id="1e06d-153">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="1e06d-153">Event ID</span></span>|  
|<span data-ttu-id="1e06d-154">MachineName</span><span class="sxs-lookup"><span data-stu-id="1e06d-154">MachineName</span></span>|<span data-ttu-id="1e06d-155">Nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="1e06d-155">Computer name</span></span>|  
|<span data-ttu-id="1e06d-156">de mensaje</span><span class="sxs-lookup"><span data-stu-id="1e06d-156">Message</span></span>|<span data-ttu-id="1e06d-157">Detalle del mensaje</span><span class="sxs-lookup"><span data-stu-id="1e06d-157">Message detail</span></span>|  
|<span data-ttu-id="1e06d-158">Source</span><span class="sxs-lookup"><span data-stu-id="1e06d-158">Source</span></span>|<span data-ttu-id="1e06d-159">Crear, actualizar, leer, eliminar, implementar o archivar los datos</span><span class="sxs-lookup"><span data-stu-id="1e06d-159">Creating, updating, reading, deleting, deploying, or archiving data</span></span>|  
|<span data-ttu-id="1e06d-160">TimeGenerated</span><span class="sxs-lookup"><span data-stu-id="1e06d-160">TimeGenerated</span></span>|<span data-ttu-id="1e06d-161">Éxito o error</span><span class="sxs-lookup"><span data-stu-id="1e06d-161">Success or Failure</span></span>|  
|<span data-ttu-id="1e06d-162">UserName</span><span class="sxs-lookup"><span data-stu-id="1e06d-162">UserName</span></span>|<span data-ttu-id="1e06d-163">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="1e06d-163">User name</span></span>|  
|<span data-ttu-id="1e06d-164">MsgGuid</span><span class="sxs-lookup"><span data-stu-id="1e06d-164">MsgGuid</span></span>|<span data-ttu-id="1e06d-165">GUID del mensaje</span><span class="sxs-lookup"><span data-stu-id="1e06d-165">Message GUID</span></span>|  
|<span data-ttu-id="1e06d-166">SvcGuid</span><span class="sxs-lookup"><span data-stu-id="1e06d-166">SvcGuid</span></span>|<span data-ttu-id="1e06d-167">GUID de servicio</span><span class="sxs-lookup"><span data-stu-id="1e06d-167">Service GUID</span></span>|  
|<span data-ttu-id="1e06d-168">Operación</span><span class="sxs-lookup"><span data-stu-id="1e06d-168">Operation</span></span>|<span data-ttu-id="1e06d-169">Detalles de la operación</span><span class="sxs-lookup"><span data-stu-id="1e06d-169">Operation detail</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e06d-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e06d-170">See Also</span></span>  
 [<span data-ttu-id="1e06d-171">Configuración del registro</span><span class="sxs-lookup"><span data-stu-id="1e06d-171">Configuring Logging</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)