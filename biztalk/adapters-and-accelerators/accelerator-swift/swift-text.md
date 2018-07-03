---
title: Texto de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, text
ms.assetid: 90851d38-7789-4b1b-813b-7943f77ab984
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06e46c8be5da2f62f2b59ce2591e0559367adf08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990933"
---
# <a name="swift-text"></a>Texto de SWIFT
El texto del mensaje conforma la carga del mensaje (FIN) financiero y contiene todos los campos de datos, excepto los campos que contienen el remitente, el receptor y el tipo de mensaje. Estos tres campos se encuentran en la parte de encabezado. Algunos mensajes contienen también un encabezado de usuario opcional, que también puede proporcionar información de procesamiento.  
  
 Cada carga de mensaje FIN consta de una serie de campos de una secuencia definida. Estos campos se ajustan a las reglas siguientes:  
  
- Los campos pueden ser obligatorio u opcional dentro de la secuencia.  
  
- Una secuencia puede contener subsecuencias, y puede que se repita una subsecuencia dentro de una secuencia.  
  
- Puede usar un campo en varios tipos de mensaje.  
  
- Dentro de un campo, puede haber elementos o subcampos. Un elemento o subcampo puede ser comunes a varios campos.  
  
- Cada secuencia repetida se representa mediante un nodo de grupo.  
  
- Cada campo puede tener varios niveles nodal, describe cada uno como un registro.  
  
- Un elemento de esquema representa sólo el subcampo de nivel más bajo.  
  
- Registros y los elementos comunes se definen en el esquema de base y comunes, como se describe a continuación.  
  
- Algunos campos se pueden representar en varios formatos (por ejemplo, los campos de entidad). Estos campos se definen como campos de elección en el esquema.  
  
  Algunos campos tienen una limitada de conjuntos de valores. En su mayor parte, el esquema muestra estos valores. Definiciones de esquema también incluyen la validación del juego de caracteres.