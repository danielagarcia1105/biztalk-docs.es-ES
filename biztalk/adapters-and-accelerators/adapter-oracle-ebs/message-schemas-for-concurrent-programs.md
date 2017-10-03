---
title: "Esquemas de mensajes para programas simultáneos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c5709d5-e2b3-485b-9cdd-004985972ba1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f475fce04e796e633359c846c339f521b6f74a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-concurrent-programs"></a>Esquemas de mensaje para programas simultáneos
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]superficies programas simultáneos como operaciones. Junto con los programas simultáneos que se exponen como operaciones, el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también expone las tres operaciones estándares siguientes: Get_Status, Wait_For_Request y Submit_Request. Para obtener información acerca de estas operaciones relacionadas con programas simultáneos, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).  
  
## <a name="message-structure-of-concurrent-program-operations"></a>Estructura de los mensajes de operaciones simultáneas de programa  
 Las operaciones que exhibe para programas simultáneos siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|[Concurrent_Program_Name] Solicitud|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name] xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]/">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <Description>[value]</Description>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_ARGUMENT1]>[value]</[CONCURRENT_PROGRAM_ARGUMENT1]>   <[CONCURRENT_PROGRAM_ARGUMENT2]>[value]</[CONCURRENT_PROGRAM_ARGUMENT2]>   … </[Concurrent_Program_Name]>`|-La operación [Concurrent_Program_Name] tiene cinco parámetros estándares: *SetOptions*, *SetPrintOptions*, *SetRepeatOptions*, *descripción* , y *StartTime*.<br /><br /> -El *ContinueOnFail* parámetro indica si el envío de solicitudes simultáneas debe continuar en caso, el parámetro parent (*SetOptions*, *SetPrintOptions* o *SetRepeatOptions*) se produce un error, o si debe producir una excepción. Puede especificar **True** (continuar) o **False** (producir una excepción).<br /><br /> -Para obtener información detallada acerca de cada parámetro, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).|  
|[Concurrent_Program_Name] Respuesta|`<?xml version="1.0" encoding="utf-8" ?> <[Concurrent_Program_Name]Response xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <[Concurrent_Program_Name]Result>[value]</[Concurrent_Program_Name]Result> </[Concurrent_Program_Name]Response>`|La respuesta de Oracle E-Business Suite contiene un identificador de solicitudes simultáneas.|  
|Solicitud de Get_Status|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>  </GetStatusForConcurrentProgram>`|Este mensaje de solicitud de Get_Status toma el identificador de solicitud de un programa simultáneo como entrada.|  
|Respuesta de Get_Status|`<?xml version="1.0" encoding="utf-8" ?> <GetStatusForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <GetStatusForConcurrentProgramResult>[value]</GetStatusForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>  </GetStatusForConcurrentProgramResponse>`|Este mensaje de respuesta de Get_Status devuelve la fase/estado de la solicitud y el mensaje de finalización de un programa simultáneo.<br /><br /> Para obtener información detallada acerca de cada parámetro, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).|  
|Solicitud de Wait_For_Request|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <RequestId>[value]</RequestId>   <Interval>[value]</Interval>   <MaxWait>[value]</MaxWait>    </WaitForRequestForConcurrentProgram>`|Para obtener información detallada acerca de cada parámetro, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).|  
|Respuesta de Wait_For_Request|`<?xml version="1.0" encoding="utf-8" ?> <WaitForRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <WaitForRequestForConcurrentProgramResult>[value]</WaitForRequestForConcurrentProgramResult>    <Phase>[value]</Phase>    <Status>[value]</Status>    <DevPhase>[value]</DevPhase>    <DevStatus>[value]</DevStatus>    <Message>[value]</Message>    </WaitForRequestForConcurrentProgramResponse>`|Este mensaje de respuesta de Wait_For_Request devuelve la fase/estado de la solicitud y el mensaje de finalización de un programa simultáneo.<br /><br /> Para obtener información detallada acerca de cada parámetro, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).|  
|Solicitud de Submit_Request|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgram xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SetOptions>     <Implicit>[value]</Implicit>     <Protected>[value]</Protected>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>     <Program>[value]</Program>   <Description>[value]</Description>   <StartTime>[value]</StartTime>   <Arguments>[array_of_strings</Arguments>    </SubmitRequestForConcurrentProgram>`|Para obtener información detallada acerca de cada parámetro, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).|  
|Respuesta de Submit_Request|`<?xml version="1.0" encoding="utf-8" ?> <SubmitRequestForConcurrentProgramResponse xmlns="[VERSION]/ConcurrentPrograms/[APP_SHORT_NAME]">   <SubmitRequestForConcurrentProgramResult>[value]</SubmitRequestForConcurrentProgramResult>  </SubmitRequestForConcurrentProgramResponse>`|Si la solicitud de envío se completa correctamente, el mensaje de respuesta devuelve el identificador de solicitudes simultáneas. En caso contrario, devuelve "0".|  
  
 Descripciones de entidad:  
  
 [Versión] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 [APP_SHORT_NAME] = nombre corto de aplicación  
  
 [CONCURRENT_PROGRAM_ARGUMENT] = argumento esperado por el programa simultáneo tal como se define en Oracle E-Business Suite  
  
## <a name="message-actions-for-concurrent-programs"></a>Acciones de mensaje para programas simultáneos  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa las siguientes acciones de mensaje para programas simultáneos.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|de mensaje|Acción|Ejemplo|  
|-------------|------------|-------------|  
|[Concurrent_Program_Name] Solicitud|ConcurrentPrograms / [APP_SHORT_NAME] / [CONCURRENT_PROGRAM_SHORT_NAME]|ConcurrentPrograms/SQLGL/ADSFINS|  
|[Concurrent_Program_Name] Respuesta|ConcurrentPrograms / [APP_SHORT_NAME] / [CONCURRENT_PROGRAM_SHORT_NAME] / respuesta|ConcurrentPrograms/SQLGL/ADSFINS/respuesta|  
|Solicitud de Get_Status|ConcurrentPrograms / [APP_SHORT_NAME] / GetStatusForConcurrentProgram|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram|  
|Respuesta de Get_Status|ConcurrentPrograms / respuesta/GetStatusForConcurrentProgram / [APP_SHORT_NAME]|ConcurrentPrograms/SQLGL/GetStatusForConcurrentProgram/respuesta|  
|Solicitud de Wait_For_Request|ConcurrentPrograms / [APP_SHORT_NAME] / WaitForRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/WaitForRequestForConcurrentProgram|  
|Respuesta de Wait_For_Request|ConcurrentPrograms / respuesta/WaitForRequestForConcurrentProgram / [APP_SHORT_NAME]|ConcurrentPrograms/SQLGL/WaitForRequestForConcurrentProgram/respuesta|  
|Solicitud de Submit_Request|ConcurrentPrograms / [APP_SHORT_NAME] / SubmitRequestForConcurrentProgram|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram|  
|Respuesta de Submit_Request|ConcurrentPrograms / respuesta/SubmitRequestForConcurrentProgram / [APP_SHORT_NAME]|ConcurrentPrograms/SQLGL/SubmitRequestForConcurrentProgram/respuesta|  
  
 Descripciones de entidad:  
  
 [APP_SHORT_NAME] = nombre corto de aplicación  
  
 [CONCURRENT_PROGRAM_SHORT_NAME] = nombre corto del programa simultáneo  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)