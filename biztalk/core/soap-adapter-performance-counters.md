---
title: Contadores de rendimiento del adaptador SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 543c982a68d2a940b4800711d757f4fb159611de
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974522"
---
# <a name="soap-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de SOAP
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: adaptador de recepción** y **BizTalk: adaptador de envío** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de recepción SOAP|Mensajes recibidos|Número total de mensajes recibidos por el adaptador de recepción SOAP. El contador aumenta cuando el adaptador lee completamente un mensaje de solicitud desde el cliente SOAP.|  
||Mensajes recibidos/s|Número de mensajes recibidos por el adaptador de recepción SOAP por segundo. El contador sólo es aplicable a los mensajes de solicitud que el adaptador ha leído completamente desde el cliente SOAP.|  
|BizTalk:Adaptador de envío SOAP|Mensajes enviados|Número total de mensajes enviados por el adaptador de envío SOAP. El contador sólo aumenta con mensajes que han alcanzado la dirección URL de destino.|  
||Mensajes enviados/s|Número de mensajes enviados por el adaptador de envío SOAP por segundo. El contador sólo es aplicable a mensajes que han alcanzado la dirección URL de destino.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-server-2008"></a>Si usa Windows Server 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**. Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.