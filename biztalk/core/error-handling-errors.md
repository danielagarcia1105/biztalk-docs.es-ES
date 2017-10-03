---
title: Error de control de errores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-handling-errors"></a>Errores de control de errores
Información para diagnosticar y resolver errores de control de errores de WCF.  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a>Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False    
||Detalles|  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Las opciones de control de errores "Deshabilitar ubicación en caso de error" y "Suspender mensaje de solicitud en caso de error" no deben establecerse ambas como False, ya que el mensaje podría perderse. Establezca una o ambas opciones como True.|  
  
## <a name="explanation"></a>Explicación  
 En el adaptador de WCF-NetMsmq, las opciones de **deshabilitar ubicación en caso de error** y **suspender el mensaje de solicitud en caso de error** deben estar ambas seleccionadas. La pérdida del mensaje puede producirse cuando la ubicación de recepción continua recibiendo mensajes no válidos y estos mensajes no se suspenden y almacenan en el cuadro de mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar las opciones del adaptador.    

1. Abra **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Seleccione **propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Seleccione **Configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, seleccione la **mensajes** ficha.  
  
9. En el **control de errores** sección, asegúrese de cualquiera **deshabilitar ubicación en caso de error** o **suspender el mensaje de solicitud en caso de error** está activada.