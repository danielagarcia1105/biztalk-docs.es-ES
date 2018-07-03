---
title: Las ubicaciones de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ee246c07fa471cefe8f4dc42f55b0543bb8419
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024266"
---
# <a name="receive-locations"></a>Ubicaciones de recepción
La creación de una ubicación de recepción conlleva especificar la dirección a la que llegan los mensajes de entrada, además de la canalización de mensajería que procesa los mensajes recibidos en dicha dirección. Solo los administradores pueden crear y habilitar las ubicaciones de recepción.  
  
 Un administrador usa la consola de administración de BizTalk para crear ubicaciones de recepción, enlazar ubicaciones de recepción con orquestaciones, habilitar ubicaciones de recepción, deshabilitar ubicaciones de recepción y establecer propiedades globales para las ubicaciones de recepción.  
  
 Un administrador (que usa la consola de administración de BizTalk) sigue estos pasos para crear una ubicación de recepción:  
  
1.  Crea una ubicación de recepción.  
  
2.  Asocia la ubicación de recepción con un host.  
  
3.  Enlaza la ubicación de recepción con una orquestación.  
  
4.  Habilita la ubicación de recepción.  
  
5.  La ubicación de recepción recibe mensajes.  
  
> [!NOTE]
>  Los cambios en las ubicaciones de recepción realizadas con el Instrumental de administración de Windows (WMI) afectan a cómo aparecen las ubicaciones de recepción en la consola de administración de BizTalk. Por ejemplo, si un administrador usa WMI para crear una nueva ubicación de recepción, esa ubicación de recepción aparece en la consola de administración de BizTalk. De forma similar, si un administrador elimina una ubicación de recepción, la ubicación de recepción desaparece de la consola de administración de BizTalk.  
> 
> [!IMPORTANT]
>  Cada ubicación de recepción debe tener un nombre único. Dos ubicaciones de recepción no puede tener el mismo nombre en el mismo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]implementación.  
> 
> [!IMPORTANT]
>  Se recomienda establecer listas de control de acceso (ACL) seguras en la ubicación de destino de las ubicaciones de recepción. Por ejemplo, debe establecer listas ACL seguras para el directorio desde el que la ubicación de recepción de archivos toma los mensajes, de modo que solo los usuarios autorizados puedan entregar mensajes en esta ubicación.  
  
## <a name="receive-location-types"></a>Tipos de ubicaciones de recepción  
 Hay dos tipos de ubicaciones de recepción:  
  
-   Unidireccional: se utiliza para las aplicaciones que entregan un mensaje sin esperar una respuesta sincrónica.  
  
-   Solicitud-respuesta: se utiliza con las aplicaciones que requieren una respuesta a un mensaje.  
  
## <a name="receive-location-properties"></a>Propiedades de la ubicación de recepción  
 Las ubicaciones de recepción tienen propiedades globales y propiedades específicas del adaptador. Los administradores, mediante la consola de administración de BizTalk, establecer propiedades globales para todas las ubicaciones de recepción asociadas con un adaptador específico.  
  
 Los cambios en las propiedades de una ubicación de recepción se producen de forma secuencial. Si un programador de soluciones modifica un valor de propiedad para una determinada ubicación de recepción, las invalidaciones de valor de propiedad nuevo el valor de propiedad global para esa ubicación de recepción que el administrador haya establecido en la consola de administración de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)   
 [Artefactos](../core/artifacts.md)