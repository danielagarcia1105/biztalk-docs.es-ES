---
title: Acerca del proceso de registro | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- logging, about logging
- auditing, about auditing
- logging
- auditing
ms.assetid: 859ee1f5-aae4-4a47-ab39-8d2b4168a429
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07dba617358d6ad451c53eeb75dbe5d1986f9066
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-logging-process"></a>Acerca del proceso de registro
Puesto que las aplicaciones controlan crítico, tiempo datos sensibles y monetario, la auditoría se convierte en una parte fundamental de la aplicación. Para habilitar la capacidad de administración de nivel de empresa y la disponibilidad, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se basa en el siguiente tiempo de ejecución compartido y componentes administrativos:  
  
-   **Registro**: recopilar y enviar todas las eventos de registro de forma administrada a una base de datos designada  
  
-   **Supervisión de eventos y la depuración del servicio**: para configurar el comportamiento de registro y para investigar o administrar la información recopilada para los administradores del sistema y otros profesionales de TI  
  
 Con la mejorada auditoría características en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], puede optimizar la eficiencia operativa, la seguridad y rendimiento para garantizar el cumplimiento con las normas de HL7.  
  
## <a name="types-of-data"></a>Tipos de datos  
 En este tema se describe distintos tipos de datos de registro utilizados por la característica de registro y que se almacenan estos datos:  
  
-   Datos de configuración: registro de los datos de configuración se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) e incluye datos de auditoría y la información de auditoría de SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Visor de eventos WMI de base de datos centralizada) ubicación.  
  
-   Los datos de archivo: registro de eventos de la tabla en el registro de SQL almacena los datos de 'Registro'.  
  
## <a name="how-logging-works"></a>Cómo funciona el registro  
 En este tema se describe los tres tipos de eventos que registra el software, así como de las tres ubicaciones donde se pueden almacenar los datos registrados.  
  
|Componente|Finalidad|  
|---------------|-------------|  
|Editor de configuración|Para especificar dónde desea guardar los datos del registro. BTAHL7 admite el registro a cualquier combinación de las siguientes acciones: registro del Visor de eventos, WMI y SQL Server.|  
|Agente de eventos|Para recibir el registro de eventos producidos por otros componentes y registrarlos en función de registro de los datos de configuración.|  
|API de registro|Interfaz de registro que se llama a todos los ensamblados de BTAHL7.|  
  
### <a name="types-of-logging"></a>Tipos de registro  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]registra los tres tipos de errores:  
  
-   Eventos informativos, servicio iniciaron o detuvieron inesperadamente o un evento de error.  
  
-   Eventos de advertencia como errores no críticos y advertencias en [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] registros de eventos. Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a un error de validación de datos.  
  
-   Eventos de error para errores críticos en un componente. Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a errores de analizador.  
  
 El sistema puede iniciar su sesión [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] eventos en configurables ubicaciones siguientes:  
  
-   [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)]Visor de eventos  
  
-   Eventos de WMI  
  
-   Base de datos centralizada (base de datos de inicio de sesión SQL)  
  
 Un agente de eventos recibe todos los [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registro de eventos y, en función de la información de configuración, envía a la ubicación adecuada.  
  
### <a name="overview-of-features"></a>Información general de características  
 El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona la característica de registro:  
  
-   Una forma unificada de registro de todos los mensajes de error  
  
-   Un repositorio centralizado para almacenar todos los detalles del evento  
  
-   Un modelo de objetos coherente para registrar los mensajes que fluyen a las aplicaciones de línea de negocio discretas  
  
-   Una combinación de registro y seguimiento le ayuda a poner en correlación los administradores del sistema ha registrado errores con documentos  
  
## <a name="event-log-data"></a>Datos de registro de eventos  
 Este tema describe el formato y el contenido de los datos de registro de eventos.  
  
 La siguiente tabla muestra los datos registrados típicos para partners.  
  
|data|Description|  
|----------|-----------------|  
|LogData|Registro de datos|  
|NúmeroDeCategoría|Número de categoría|  
|EntryType|Tipo del evento|  
|Id. de evento|Identificador del evento|  
|MachineName|Nombre del equipo|  
|de mensaje|Detalles del mensaje|  
|Source|Crear, actualizar, leer, eliminar, implementar o archivar los datos|  
|TimeGenerated|Éxito o error|  
|UserName|Nombre de usuario.|  
|MsgGuid|GUID del mensaje|  
|SvcGuid|GUID de servicio|  
|Operación|Detalles de la operación|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el registro](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)