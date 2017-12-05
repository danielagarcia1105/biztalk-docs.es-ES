---
title: "Cómo usar el modificador ThrowDetailedError | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90929015e2d1d0567af0ccc5c51c6aae450d49c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a>Cómo usar el modificador ThrowDetailedError
Si se produce un error, el cliente Web recibe un tipo genérico **SoapException**.  
  
 Para depurar el servicio Web publicado, puede agregar un modificador al archivo Web.config para controlar el nivel de los detalles de la excepción devueltos desde el servicio Web publicado.  
  
 El archivo Web.config contiene un modificador de la configuración de aplicación, **ThrowDetailedError**. **False** es el valor predeterminado de **ThrowDetailedError**. Si cambia la configuración a **True**, el servidor proxy devuelve información de excepción interna para el cliente Web, lo que le permite depurar el servicio Web publicado.  
  
 El código XML siguiente muestra el **ThrowDetailedError** conmutador que aparece en el archivo Web.config bajo el \<appSettings\> nodo:  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  BizTalk Server no devuelve información de excepción interior al cliente Web de forma predeterminada porque puede contener información confidencial, como pilas de llamadas de aplicación. Tras la depuración, debe establecer el **ThrowDetailedError** si se establece en **False**.  
  
## <a name="see-also"></a>Vea también  
 [Depuración de servicios web publicados](../core/debugging-published-web-services.md)