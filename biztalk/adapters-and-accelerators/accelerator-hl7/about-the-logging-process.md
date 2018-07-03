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
# <a name="about-the-logging-process"></a>Acerca del proceso de registro
Puesto que las aplicaciones controlan críticos, tiempo datos confidenciales y monetario, la auditoría se convierte en una parte fundamental de la aplicación. Para habilitar la capacidad de administración de nivel de empresa y la disponibilidad, Microsoft [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se basa en el siguiente tiempo de ejecución compartido y los componentes administrativos:  
  
- **Registro**: recopilar y enviar todos los eventos de registro de forma administrada a una base de datos designada  
  
- **Supervisión de eventos y la depuración del servicio**: para configurar el comportamiento del registro y para investigar y administrar la información recopilada para los administradores del sistema y otros profesionales de TI  
  
  Con una mejora las características de auditoría de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], puede optimizar la eficacia operativa, seguridad y rendimiento para garantizar el cumplimiento con las normas de HL7.  
  
## <a name="types-of-data"></a>Tipos de datos  
 En este tema se describe los distintos tipos de datos de registro utilizados por la característica de registro y que se almacenan estos datos:  
  
- Datos de configuración: registro de los datos de configuración se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) e incluye datos de auditoría y la información de auditoría de SQL ([!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Visor de eventos WMI de base de datos centralizada) ubicación.  
  
- Los datos de archivo: registro de eventos de la tabla en el registro de SQL almacena los datos de 'Registro'.  
  
## <a name="how-logging-works"></a>Cómo funciona el registro  
 En este tema se describe los tres tipos de eventos que registra el software, así como las tres ubicaciones donde puede almacenar los datos registrados.  
  
|Componente|Finalidad|  
|---------------|-------------|  
|Editor de configuración|Para especificar dónde guardar los datos de registro. BTAHL7 admite el registro a cualquier combinación de las siguientes acciones: registro del Visor de eventos, WMI y SQL Server.|  
|Agente de eventos|Para recibir el registro de eventos producidos por otros componentes y los registre en función de registro de los datos de configuración.|  
|API de registro|Interfaz de registro que se llama a todos los ensamblados de BTAHL7.|  
  
### <a name="types-of-logging"></a>Tipos de registro  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registra los tres tipos de errores:  
  
- Error en un servicio iniciado o detenido, un evento o eventos informativos.  
  
- Eventos de advertencia como errores no críticos y advertencias en [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] los registros de eventos. Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a un error de validación de datos.  
  
- Eventos de error para errores críticos en un componente. Por ejemplo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] suspende un mensaje debido a errores del analizador.  
  
  Puede iniciar el sistema [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] eventos en las siguientes ubicaciones configurables:  
  
- [!INCLUDE[btsWinNTNoVersion](../../includes/btswinntnoversion-md.md)] Visor de eventos  
  
- Eventos de WMI  
  
- Base de datos centralizada (registro de SQL database)  
  
  Un agente de eventos recibe todos los [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] registro de eventos y, en función de la información de configuración, envía a la ubicación adecuada.  
  
### <a name="overview-of-features"></a>Información general de características  
 El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proporciona la característica de registro:  
  
-   Una manera unificada de inicio de sesión de todos los mensajes de error  
  
-   Un repositorio centralizado para almacenar todos los detalles del evento  
  
-   Un modelo de objetos coherente para registrar mensajes que fluyen a las aplicaciones de línea de negocio discretas  
  
-   Una combinación de registro y seguimiento para correlacionan los administradores del sistema de ayuda se ha registrado errores con documentos  
  
## <a name="event-log-data"></a>Datos de registro de eventos  
 Este tema describe el formato y contenido de los datos de registro de eventos.  
  
 La siguiente tabla muestra los datos registrados típicos para partners.  
  
|data|Descripción|  
|----------|-----------------|  
|LogData|Registro de datos|  
|NúmeroDeCategoría|Número de categoría|  
|EntryType|Tipo del evento|  
|EventId|Identificador del evento|  
|MachineName|Nombre del equipo|  
|de mensaje|Detalle del mensaje|  
|Source|Crear, actualizar, leer, eliminar, implementar o archivar los datos|  
|TimeGenerated|Éxito o error|  
|UserName|Nombre de usuario|  
|MsgGuid|GUID del mensaje|  
|SvcGuid|GUID de servicio|  
|Operación|Detalles de la operación|  
  
## <a name="see-also"></a>Vea también  
 [Configuración del registro](../../adapters-and-accelerators/accelerator-hl7/configuring-logging.md)