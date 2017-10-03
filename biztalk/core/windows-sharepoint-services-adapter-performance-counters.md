---
title: Contadores de rendimiento del adaptador de Windows SharePoint Services | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41583fde-530a-4070-9647-f1ab6273aadf
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80340fd8479b8bf1a0e431e90778f7501763fe4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter-performance-counters"></a>Contadores de rendimiento del adaptador de Windows SharePoint Services
Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema. Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.  
  
 Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: adaptador de servicios de Sharepoint** categoría de objeto de rendimiento:  
  
|**Categoría**|**Contador**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Adaptador de Windows SharePoint Services|% de errores de recepción de mensaje|Porcentaje de archivos de Windows SharePoint Services que no ha procesado BizTalk Server debido a errores de recepción.|  
||% de errores de envío de mensaje|Porcentaje de mensajes con errores que BizTalk Server intentó enviar a Windows SharePoint Services.|  
||% de errores de llamadas a servicios Web|Porcentaje de errores en llamadas de los servicios Web del adaptador de Windows SharePoint Services.|  
||Total de errores de aplicación de recepción|Número total de errores de Windows SharePoint Services que se generaron al actualizar el estado de los documentos de SharePoint.|  
||Total de errores de recepción de mensajes|Número total de archivos de Windows SharePoint Services recibidos que no ha procesado BizTalk Server debido a errores de recepción.|  
||Total de mensajes recibidos|Número total de archivos de Windows SharePoint Services recibidos por el adaptador de Windows SharePoint Services, incluidos los archivos que no se pudieron procesar.|  
||Total de errores de envío de mensajes|Número total de mensajes con errores que BizTalk Server intentó enviar a Windows SharePoint Services.|  
||Total de mensajes enviados|Número total de mensajes que BizTalk Server envió a Windows SharePoint Services, incluidos los archivos que no se han podido procesar.|  
||Total de errores de llamadas a servicios Web|Número total de errores en llamadas de los servicios Web del adaptador de Windows SharePoint Services.|  
||Llamadas a servicios Web por segundo|Número de errores en llamadas de los servicios Web del adaptador de Windows SharePoint Services por segundo.|  
  
## <a name="to-access-performance-counters"></a>Para tener acceso a los contadores de rendimiento  
 Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.  
  
#### <a name="if-you-are-using-windows-2008"></a>Si está usando Windows 2008  
  
1.  Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.  
  
2.  En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.  
  
3.  En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk: adaptador de servicios de Sharepoint** objeto de contador de rendimiento y seleccione los contadores que desea supervisar  
  
4.  En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.  Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.  
  
5.  Después de agregar los contadores, haga clic en **Aceptar**.  
  
     Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.