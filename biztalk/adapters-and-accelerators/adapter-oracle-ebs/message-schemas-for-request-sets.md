---
title: Esquemas de mensajes para los conjuntos de solicitud | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bba9677d-ee94-4da5-8611-b1e47f2f3798
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fd81ee75088b41a182c5a2aa675266420f8f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217100"
---
# <a name="message-schemas-for-request-sets"></a>Esquemas de mensaje para conjuntos de solicitudes
Aparece como una operación en cada solicitud que se establezcan en una aplicación de Oracle en Oracle E-Business Suite [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  
  
## <a name="message-structure-of-request-set-operation"></a>Estructura de mensaje de solicitud de la operación del conjunto  
 Las operaciones que exhibe para conjunto de solicitud siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|[Request_Set_Name] Solicitud|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name] xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]/">   <SetRelClassOptions>     <Application>[value]</Application>     <ClassName>[value]</ClassName>     <CancelOrHold>[value]</CancelOrHold>     <StaleDate>[value]</StaleDate>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRelClassOptions>   <SetPrintOptions>     <Printer>[value]</Printer>     <Style>[value]</Style>     <Copies>[value]</Copies>     <SaveOutput>[value]</SaveOutput>     <PrintTogether>[value]</PrintTogether>     <ContinueOnFail>[value]</ContinueOnFail>   </SetPrintOptions>   <SetRepeatOptions>     <RepeatTime>[value]</RepeatTime>     <RepeatInterval>[value]</RepeatInterval>     <RepeatUnit>[value]</RepeatUnit>     <RepeatType>[value]</RepeatType>     <RepeatEndTime>[value]</RepeatEndTime>     <ContinueOnFail>[value]</ContinueOnFail>   </SetRepeatOptions>   <SetNlsOptions>     <Language>[value]</Language>     <Territory>[value]</Territory>     <ContinueOnFail>[value]</ContinueOnFail>   </SetNlsOptions>   <StartTime><[value]</StartTime>   <[CONCURRENT_PROGRAM_NAME1]>[value]</[CONCURRENT_PROGRAM_NAME1]>   <[CONCURRENT_PROGRAM_NAME2]>[value]</[CONCURRENT_PROGRAM_NAME2]>   … </[Request_Set_Name]>`|-La operación [Request_Set_Name] tiene cinco parámetros estándares: `SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions`, `SetNlsOptions`, y `StartTime`.<br /><br /> -El `ContinueOnFail` parámetro indica si el envío de conjunto de solicitud debe continuar o se produce una excepción en caso del parámetro parent (`SetRelClassOptions`, `SetPrintOptions`, `SetRepeatOptions` o `SetNlsOptions`) se produce un error. Puede especificar **True** (continuar) o **False** (producir una excepción).<br /><br /> -Para obtener información detallada acerca de cada parámetro, consulte [operaciones con conjuntos de solicitud](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).|  
|[Request_Set_Name] Respuesta|`<?xml version="1.0" encoding="utf-8" ?> <[Request_Set_Name]Response xmlns="[VERSION]/RequestSets/[APP_SHORT_NAME]">   <[Request_Set_Name]Result>[value]</[Request_Set_Name]Result> </[Request_Set_Name]Response>`|La respuesta de Oracle E-Business Suite contiene un identificador de solicitudes simultáneas.|  
  
 Descripciones de entidad:  
  
 [Versión] = http://schemas.microsoft.com/OracleEBS/2008/05  
  
 .  
  
 [CONCURRENT_PROGRAM_NAME] = simultánea programa incluido en el conjunto de solicitud.  
  
## <a name="message-actions-for-request-sets"></a>Acciones de mensaje para conjuntos de solicitudes  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa las siguientes acciones de mensaje para conjuntos de solicitudes.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|de mensaje|Acción|Ejemplo|  
|-------------|------------|-------------|  
|Solicitud de conjunto de solicitud|RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]|RequestSets/SQLGL/FNDRSSUB965|  
|Conjunto de solicitud-respuesta|RequestSets / [APP_SHORT_NAME] / [REQUESTSET_SHORT_NAME]] / respuesta|RequestSets/SQLGL/FNDRSSUB965/respuesta|  
  
 Descripciones de entidad:  
  
 [APP_SHORT_NAME] = nombre corto de aplicación.  
  
 [REQUESTSET_SHORT_NAME] = solicitud establecer nombre corto.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)