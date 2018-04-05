---
title: 'Advertencia: XML de extensión personalizada pero no hay XSLT personalizado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a>Advertencia: XML de extensión personalizada pero no hay XSLT personalizado
**Código de error**  
  
 btm1033  
  
 **Explicación**  
  
 El **XML de extensión personalizada** ha reemplazado la propiedad sin el **ruta de XSLT personalizada** que se reemplazara propiedad. Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.  
  
 El Asignador de BizTalk utilizará el XSLT generado mediante la compilación de la asignación y también generará el XML de extensión y lo anexará al XML de extensión personalizada especificado por la propiedad reemplazada. Esto puede resultar útil si la asignación contiene **secuencias de comandos** plantillas que realicen llamadas a uno o más métodos de los ensamblados externos de llamadas de functoids que utilicen XSLT en línea o XSLT en línea. En tales casos, el usuario, a continuación, puede especificar el prefijo de asignación de nombre de ensamblado en el **XML de extensión personalizada** propiedad.  
  
 **Acción del usuario**  
  
 Si la condición indicada por esta advertencia no era intencionada, escriba un valor compatible para la **ruta de XSLT personalizada** propiedad o quite la invalidación del valor para el **XML de extensión personalizada** propiedad.