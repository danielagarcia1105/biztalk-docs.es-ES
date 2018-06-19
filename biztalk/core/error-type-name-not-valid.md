---
title: 'Error: nombre de tipo no válido | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.typeNameNotValid
ms.assetid: 4c9bceeb-b009-4279-ad16-19af09e6b091
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dac6d85d3b16ec691a4cc73b179515b70686791
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241420"
---
# <a name="error---type-name-not-valid"></a>Error: nombre de tipo no válido
**Código de error**  
  
 BEC2011  
  
 **Explicación**  
  
 El **nombre de tipo** propiedad de este archivo de esquema no es válida. Dado que el valor de la **nombre de tipo** propiedad se utiliza como el nombre de un nombre de clase de C# generado automáticamente, debe ser un identificador C# válido y no puede ser una palabra clave de BizTalk reservada.  
  
 **Acción del usuario**  
  
 Seleccione el archivo de esquema correspondiente en Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones y, a continuación, en la ventana Propiedades, cambie la **nombre de tipo** propiedad en un valor que es un identificador válido de C# y no es una palabra clave de BizTalk reservada.