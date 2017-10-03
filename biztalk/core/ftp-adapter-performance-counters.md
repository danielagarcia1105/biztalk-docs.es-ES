---
title: Contadores de rendimiento del adaptador FTP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5cbe67-9aa3-4194-816e-fab4eb551c07
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9349e0d58671c783b9e1691c3bbcd4080e7f4b7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ftp-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de FTP
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **adaptador de recepción FTP** y **adaptador de envío FTP** categorías de objetos de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de recepción FTP|Bytes recibidos|Número total de bytes recibidos por el adaptador de recepción FTP. El contador aumenta cuando el adaptador de recepción FTP lee completamente un mensaje desde el servidor FTP.|  
||Bytes recibidos/seg.|Número de bytes recibidos por el adaptador de recepción FTP por segundo. El contador solo es aplicable a los mensajes que el adaptador de recepción FTP ha leído completamente desde el servidor FTP.|  
||Mensajes recibidos|Número total de mensajes recibidos por el adaptador de recepción FTP. El contador aumenta cuando el adaptador de recepción FTP lee completamente un mensaje desde el servidor FTP.|  
||Mensajes recibidos/s|Número de mensajes recibidos por el adaptador de recepción FTP por segundo. El contador solo es aplicable a los mensajes que el adaptador de recepción FTP ha leído completamente desde el servidor FTP.|  
|BizTalk:Adaptador de envío FTP|Bytes enviados|Número total de bytes enviados por el adaptador de envío FTP. El contador solo aumenta con mensajes que se han escrito correctamente en los servidores FTP de destino.|  
||Bytes enviados/seg.|Número de bytes enviados por el adaptador de envío FTP por segundo. El contador se aplica sólo a los mensajes que se han escrito en el servidor FTP de destino.|  
||Mensajes enviados|Número total de mensajes enviados por el adaptador de envío FTP. El contador solo aumenta con mensajes que se han escrito correctamente en los servidores FTP de destino.|  
||Mensajes enviados/s|Número de mensajes enviados por el adaptador de envío FTP por segundo. El contador solo es aplicable a mensajes que se han escrito en el servidor FTP de destino.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **FTP** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de BizTalk Server](../core/monitoring-biztalk-server.md) [consideraciones para ejecutar controladores del adaptador en un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)