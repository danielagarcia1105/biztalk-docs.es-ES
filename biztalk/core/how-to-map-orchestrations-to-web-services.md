---
title: Cómo asignar orquestaciones a servicios Web | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f624c94a22efbfa56ae533ff9bfdbf3276776f8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998589"
---
# <a name="how-to-map-orchestrations-to-web-services"></a>Cómo asignar orquestaciones a servicios Web
Una orquestación puede tener varios puertos de recepción. Mediante el Asistente para publicar servicios Web de BizTalk, se seleccionan los puertos de recepción para publicarlos como servicios Web. El asistente crea un servicio Web (.archivo asmx) para cada puerto de recepción. El asistente también puede crear un servicio Web para todos los puertos de recepción sin son del mismo tipo (unidireccionales o de solicitud-respuesta). Las operaciones se convierten en llamadas de función. Cada operación del puerto de recepción se convierte en un método Web. Las operaciones de solicitud se convierten en parámetros de entrada. Las operaciones de respuesta se convierten en tipos de devolución.  
  
 Si las operaciones de solicitud y respuesta son del mismo tipo de mensaje Web, el parámetro de entrada se convierte en un **ref** y el tipo de valor devuelto es **void**. Los clientes Web ASP.NET pueden cambiar la firma del método Web mediante la combinación de parámetros de entrada y salida del mismo tipo. Por ejemplo, un cliente Web de ASP.NET puede cambiar a un método BizTalk Web desde **string myService (parte de la cadena)** a **void myService (parte de la cadena ref)**.  
  
 Los tipos de mensaje de operación definen las firmas de los métodos Web. Cada parte del tipo de mensaje representa un parámetro del método Web.  
  
## <a name="message-type-part-names-and-target-namespaces"></a>Nombres de partes de tipos de mensajes y espacio de nombres de destino  
 Esquemas de documentos y las clases definidas por el usuario con **XmlRootAttribute** especificado es partes de tipo que han definido los espacios de nombres de destino de mensaje. Los esquemas EDI, las clases definidas por el usuario sin **XmlRootAttribute** especificados y los tipos integrados, como **System.String** son partes de tipo de mensaje sin espacios de nombres de destino definido.  
  
|Si el nombre de parte de tipo de mensaje tiene un|Nombre de parámetro utilizado|  
|-----------------------------------------|-------------------------|  
|Espacio de nombres de destino definido|Nombre de elemento raíz|  
|Ningún espacio de nombres de destino definido|Nombre de parte de tipo de mensaje|  
  
> [!NOTE]
>  Cuando se usa un tipo de mensaje de varias partes para el mensaje de respuesta, el Asistente para publicar servicios Web de BizTalk usa la primera parte para el valor de devolución y las demás partes como parámetros de salida.  
  
## <a name="orchestrations-with-multiple-operations"></a>Orquestaciones con varias operaciones  
 Si la orquestación tiene varias operaciones, debería diseñarla para que tenga un puerto de recepción en lugar de varios. Este diseño evita que el Asistente para publicar servicios Web de BizTalk crea varios archivos de Web (.asmx) de servicio y solo funciona cuando todas las operaciones tienen el mismo patrón que realiza la llamada: todas las operaciones unidireccionales o todas las operaciones de solicitud-respuesta. Un puerto único de recepción no puede contener operaciones unidireccionales y de solicitud-respuesta al mismo tiempo.  
  
> [!NOTE]
>  El Asistente para publicar servicios Web de BizTalk muestra los puertos de recepción públicos, que son tipos de puertos con un modificador de tipo público. Sólo se pueden publicar puertos públicos como servicios Web. El tipo de puerto predeterminado es interno.  
  
> [!NOTE]
>  Si la recepción puerto está definido como unidireccional, el tipo de respuesta de método Web es **void** y se devuelve ninguna información al cliente Web. Las excepciones que inicia el adaptador de SOAP o una orquestación no se devuelven al cliente Web.  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Convenciones de nomenclatura de servicios Web para orquestaciones publicadas  
 El Asistente para publicar servicios Web de BizTalk genera nombres de archivo (.asmx) del servicio Web basados en el espacio de nombres de las orquestaciones, seguido por un carácter de subrayado (*), seguido por el nombre de tipo, seguido por un carácter de subrayado (\\*), y seguido del nombre del puerto de recepción. Un carácter de subrayado (\_) reemplaza a cualquiera de los elementos que contengan puntos. El nombre del servicio Web siempre tiene el nombre del puerto agregado.  
  
 En la tabla siguiente se muestra cómo el Asistente para publicar servicios Web de BizTalk genera nombres de servicios Web.  
  
|Orquestaciones con puertos Web|Nombre del servicio Web generado|  
|-------------------------------------------|--------------------------------|  
|Una orquestación con un puerto Web|orchestration1_port1.asmx|  
|Una orquestación con dos puertos Web|orchestration1_port1.asmx y orchestration1_port2.asmx|  
|Dos orquestaciones con un puerto Web cada uno|orchestration1_port1.asmx y orchestration2_port2.asmx|  
  
## <a name="see-also"></a>Vea también  
 [Publicar una orquestación como un servicio Web](../core/publishing-an-orchestration-as-a-web-service.md)   
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como un servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)