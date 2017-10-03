---
title: "¿Qué es un controlador de adaptador? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- handlers [adapters]
- adapters, handlers
- handlers [adapters], about handlers
ms.assetid: 4d1afa39-6320-467f-a7e8-f5f18236648e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8a1b60661427776dd4e35ffce27bf120bf94a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-an-adapter-handler"></a>¿Qué es un controlador de adaptador?
Un controlador de adaptador es una instancia de un host de BizTalk en la que se ejecuta el código de adaptador. Al especificar un controlador de envío o de recepción para un adaptador, está especificando la instancia de host en la que se ejecutará el código de adaptador. Un controlador de adaptador se encarga de la ejecución del adaptador, y contiene las propiedades de una instancia de adaptador específica. La configuración predeterminada de BizTalk Server creará controladores de adaptador para todos los adaptadores instalados, aunque puede que desee crear adaptadores adicionales para equilibrar la carga, o bien para aislar los procesos de un determinado controlador de adaptador.  
  
 Los controladores de adaptador están asociados a una instancia de host de BizTalk, y las instancias de host de BizTalk están, a su vez, asociadas a un servidor de BizTalk. Por tanto, deberá agregar servidores BizTalk adicionales al grupo de BizTalk si desea equilibrar la carga de procesamiento de los adaptadores en todos los servidores de BizTalk. No es necesario que agregue servidores de BizTalk adicionales al grupo de BizTalk si está creando controladores de adaptador adicionales con fines de aislamiento de procesos.  
  
 Si necesita crear una instancia de host nueva para ejecutar un controlador de adaptador, primero deberá crear un host y, a continuación, crear una instancia de ese host para que se ejecute en uno de los servidores de BizTalk. Para obtener más información, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md) y [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).  
  
 Todos los controladores de adaptador, a excepción de los controladores de recepción de adaptadores de HTTP y SOAP, deben configurarse de tal forma que se ejecuten en un host en curso. Los controladores de adaptador de HTTP y de SOAP sólo pueden ejecutarse en hosts aislados.  
  
## <a name="see-also"></a>Vea también  
 [Crear y eliminar controladores de adaptador](../core/creating-and-deleting-adapter-handlers.md)