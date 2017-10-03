---
title: "Cómo asignar orquestaciones a servicios Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f101a9a9ab6c0d99e9895433401de08b1380d1e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-orchestrations-to-web-services"></a>Cómo asignar orquestaciones a servicios Web
Una orquestación puede tener varios puertos de recepción. Mediante el Asistente para publicar servicios Web de BizTalk, se seleccionan los puertos de recepción para publicarlos como servicios Web. El asistente crea un servicio Web (.archivo asmx) para cada puerto de recepción. El asistente también puede crear un servicio Web para todos los puertos de recepción sin son del mismo tipo (unidireccionales o de solicitud-respuesta). Las operaciones se convierten en llamadas de función. Cada operación del puerto de recepción se convierte en un método Web. Las operaciones de solicitud se convierten en parámetros de entrada. Las operaciones de respuesta se convierten en tipos de devolución.  
  
 Si las operaciones de solicitud y respuesta son del mismo tipo de mensaje de Web, el parámetro de entrada se convierte en una **ref** y el tipo de valor devuelto es **void**. Los clientes Web ASP.NET pueden cambiar la firma del método Web mediante la combinación de parámetros de entrada y salida del mismo tipo. Por ejemplo, un cliente Web de ASP.NET puede cambiar un método Web de BizTalk desde **string myService (parte de la cadena)** a **void myService (parte de cadena ref)**.  
  
 Los tipos de mensaje de operación definen las firmas de los métodos Web. Cada parte del tipo de mensaje representa un parámetro del método Web.  
  
## <a name="message-type-part-names-and-target-namespaces"></a>Nombres de partes de tipos de mensajes y espacio de nombres de destino  
 Esquemas de documentos y las clases definidas por el usuario con **XmlRootAttribute** especificado es partes de tipo que han definido los espacios de nombres de destino de mensaje. Esquemas EDI, clases definidas por el usuario sin **XmlRootAttribute** especificados y los tipos integrados, como **System.String** son partes de tipo de mensaje sin espacios de nombres de destino definidos.  
  
|Si el nombre de parte de tipo de mensaje tiene un|Nombre de parámetro utilizado|  
|-----------------------------------------|-------------------------|  
|Espacio de nombres de destino definido|Nombre de elemento raíz|  
|Ningún espacio de nombres de destino definido|Nombre de parte de tipo de mensaje|  
  
> [!NOTE]
>  Cuando se usa un tipo de mensaje de varias partes para el mensaje de respuesta, el Asistente para publicar servicios Web de BizTalk usa la primera parte para el valor de devolución y las demás partes como parámetros de salida.  
  
## <a name="orchestrations-with-multiple-operations"></a>Orquestaciones con varias operaciones  
 Si la orquestación tiene varias operaciones, debería diseñarla para que tenga un puerto de recepción en lugar de varios. Este diseño evita que el Asistente para publicación de servicios Web de BizTalk crea varios archivos de Web (.asmx) de servicio y solo funciona cuando todas las operaciones tienen el mismo patrón que realiza la llamada, todas las operaciones unidireccionales o todas las operaciones de solicitud-respuesta. Un puerto único de recepción no puede contener operaciones unidireccionales y de solicitud-respuesta al mismo tiempo.  
  
> [!NOTE]
>  El Asistente para publicar servicios Web de BizTalk muestra los puertos de recepción públicos, que son tipos de puertos con un modificador de tipo público. Sólo se pueden publicar puertos públicos como servicios Web. El tipo de puerto predeterminado es interno.  
  
> [!NOTE]
>  Si la recepción puerto está definido como unidireccional, el tipo de respuesta de método Web es **void** y no se devuelve información al cliente Web. Las excepciones que inicia el adaptador de SOAP o una orquestación no se devuelven al cliente Web.  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Convenciones de nomenclatura de servicios Web para orquestaciones publicadas  
 El Asistente para publicación de servicios Web de BizTalk genera nombres de archivo de Web (.asmx) de servicio basados en el espacio de nombres de orquestaciones, seguido por un carácter de subrayado (_), seguido del nombre de tipo, seguido por un carácter de subrayado (\_) y seguido por el nombre de la recepción puerto. Un carácter de subrayado (\_) reemplaza cualquiera de los elementos que contengan puntos. El nombre del servicio Web siempre tiene el nombre del puerto agregado.  
  
 En la tabla siguiente se muestra cómo el Asistente para publicar servicios Web de BizTalk genera nombres de servicios Web.  
  
|Orquestaciones con puertos Web|Nombre del servicio Web generado|  
|-------------------------------------------|--------------------------------|  
|Una orquestación con un puerto Web|orchestration1_port1.asmx|  
|Una orquestación con dos puertos Web|orchestration1_port1.asmx y orchestration1_port2.asmx|  
|Dos orquestaciones con un puerto Web cada uno|orchestration1_port1.asmx y orchestration2_port2.asmx|  
  
## <a name="see-also"></a>Vea también  
 [Publicar una orquestación como servicio Web](../core/publishing-an-orchestration-as-a-web-service.md)   
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)