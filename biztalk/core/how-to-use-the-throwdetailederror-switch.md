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
ms.openlocfilehash: 194306da3b021e7460b88a3d8e76801a2eeaebba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a>Cómo usar el modificador ThrowDetailedError
Si se produce un error, el cliente Web recibe un tipo genérico **SoapException**.  
  
 Para depurar el servicio Web publicado, puede agregar un modificador al archivo Web.config para controlar el nivel de los detalles de la excepción devueltos desde el servicio Web publicado.  
  
 El archivo Web.config contiene un modificador de la configuración de aplicación, **ThrowDetailedError**. **False** es el valor predeterminado de **ThrowDetailedError**. Si cambia la configuración a **True**, el servidor proxy devuelve información de excepción interna para el cliente Web, lo que le permite depurar el servicio Web publicado.  
  
 El código XML siguiente muestra el **ThrowDetailedError** conmutador que aparece en el archivo Web.config bajo el \<appSettings > nodo:  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  BizTalk Server no devuelve información de excepción interior al cliente Web de forma predeterminada porque puede contener información confidencial, como pilas de llamadas de aplicación. Tras la depuración, debe establecer el **ThrowDetailedError** si se establece en **False**.  
  
## <a name="see-also"></a>Vea también  
 [Depurar servicios Web publicados](../core/debugging-published-web-services.md)