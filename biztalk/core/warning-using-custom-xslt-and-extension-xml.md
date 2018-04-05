---
title: 'Advertencia: utilizando XSLT personalizado y la extensión XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90644aec738345e3a36286cc62aaa7a355e04348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a>Advertencia: se está utilizando XSLT personalizado y XML de extensión
**Código de error**  
  
 btm1035  
  
 **Explicación**  
  
 Los valores de la presencia de invalidación para el **ruta de XSLT personalizada** y **XML de extensión personalizada** controla los mensajes de instancia de salida generados por esta asignación, omite por completo las asignaciones de propiedades especificar entre los esquemas de origen y de destino. Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.  
  
 Un escenario en que esto es válido consiste en utilizar el asignador de BizTalk para generar un XSLT preliminar para la asignación, modifique el XSLT manualmente para que cumpla requisitos adicionales específicos y, a continuación, especifique el archivo modificado como valor de la **ruta de XSLT personalizada** propiedad, con lo que se reemplaza el XSLT preliminar durante las operaciones de asignación posteriores.  
  
 **Acción del usuario**  
  
 Si no desea reemplazar la asignación especificada en esta asignación, quite los valores de invalidación para el **ruta de XSLT personalizada** propiedad y el **XML de extensión personalizada** propiedad, según corresponda.