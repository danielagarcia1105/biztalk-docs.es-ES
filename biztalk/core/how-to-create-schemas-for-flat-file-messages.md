---
title: Cómo crear esquemas para mensajes de archivo sin formato | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4459012155ca95166b6345ddad4390e78fce60c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984469"
---
# <a name="create-schemas-for-flat-file-messages"></a>Crear esquemas para mensajes de archivo sin formato

## <a name="overview"></a>Información general
Después de crear un esquema de mensaje XML como se describe en [crear esquemas para mensajes XML](../core/how-to-create-schemas-for-xml-messages.md), utilice el **extensiones de Editor de esquemas** propiedad de la **esquema** nodo para habilitar el extensión de archivo sin formato. La habilitación de la extensión de archivo sin formato agrega un número considerable de propiedades a muchos de los tipos de nodos de un esquema. Estas propiedades se utilizan normalmente para controlar cómo se traduce un documento empresarial de archivo sin formato a su equivalente XML, o a la inversa, y los valores se almacenan como anotaciones del lenguaje de definición de esquemas XML dentro del archivo de esquema. Utilizar correctamente estas propiedades requiere algo de práctica y un amplio conocimiento de los aspectos que rigen el formato de los archivos sin formato. 

Para conceptual e información acerca de las propiedades de archivo sin formato de referencia, vea [consideraciones al crear mensajes esquemas de archivo plano](../core/considerations-when-creating-flat-file-message-schemas.md) y **propiedades de nodo adicionales para los esquemas de archivo sin formato** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  

## <a name="see-also"></a>Vea también  
- [Administración de esquemas en proyectos](../core/managing-schemas-within-projects.md)
- Para obtener más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
