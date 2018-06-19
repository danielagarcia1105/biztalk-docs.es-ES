---
title: Planificación para publicar Web Services2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0b9d593a3309f7b4477f2fa735f7e265b614c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264460"
---
# <a name="planning-for-publishing-web-services"></a>Planificación para publicar servicios Web
Se puede obtener acceso a los servicios Web desde las orquestaciones. Además, el Asistente para publicar servicios Web de BizTalk permite publicar el servicio Web.  
  
 En la tabla siguiente se enumeran algunas de las preguntas que es preciso responder al planear los servicios Web.  
  
|Pregunta preliminar|Recomendación|  
|-----------------------|--------------------|  
|¿Ha generado el proyecto de BizTalk Server?|Antes de ejecutar el Asistente para publicar servicios Web de BizTalk, debe crear el proyecto de BizTalk Server.|  
|¿Ha habilitado el sistema para ejecutar los servicios Web?|Debe habilitar los servicios Web en el equipo antes de ejecutar el Asistente para publicar servicios Web de BizTalk. Para obtener más información acerca de cómo habilitar el sistema para servicios Web, consulte [habilitar servicios Web](../core/enabling-web-services.md).|  
|¿Ha comprobado que el esquema contiene sólo caracteres y elementos XML válidos?|Los servicios Web no admiten caracteres de extensión A de ideogramas unificados de chino, japonés o coreano (CJK). Además, hay restricciones en determinados elementos del esquema XML (XSD). Para obtener más información acerca de los caracteres XML válidos, elementos admitidos y consideraciones sobre los elementos, vea [consideraciones al publicar servicios Web](../core/considerations-when-publishing-web-services.md).|  
|¿Algún tipo de mensaje del proyecto de BizTalk Server utiliza clases .NET definidas por el usuario?|Debe instalar los ensamblados que contienen clases .NET definidas por el usuario a las que los tipos de mensajes hacen referencia en la caché de ensamblados global (GAC).|  
|¿Usan los clientes Web las credenciales proporcionadas para el **WindowsUser** propiedad de contexto?|Las credenciales proporcionadas por los clientes Web consumir un servicio Web publicado usan la **WindowsUser** propiedad de contexto. La resolución de entidades usa esta propiedad. Si configura una entidad utilizando la **WindowsUser** propiedad de contexto y el cliente Web consume el servicio Web con credenciales que coinciden con la entidad, BizTalk Server identifica el mensaje como procedente de la entidad predefinida correspondiente. Para obtener más información acerca de la resolución de entidades con componentes de canalización, consulte [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).|  
  
## <a name="see-also"></a>Vea también  
 [Publicar servicios Web](../core/publishing-web-services.md)