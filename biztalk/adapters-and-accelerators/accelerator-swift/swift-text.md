---
title: Texto SWIFT | Documentos de Microsoft
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
ms.openlocfilehash: c80d8ee0343cbf8ac96d57119ef198d623159b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-text"></a>Texto SWIFT
El texto del mensaje constituye la carga del mensaje (FIN) financiero y contiene todos los campos de datos excepto los campos que contienen el remitente, el receptor y el tipo de mensaje. Estos tres campos se encuentran en la parte de encabezado. Algunos mensajes también contienen un encabezado de usuario opcionales, que también puede proporcionar información de procesamiento.  
  
 Cada carga de mensaje FIN está formada por una serie de campos de una secuencia definida. Estos campos se ajustan a las siguientes reglas:  
  
-   Los campos pueden estar obligatorio u opcional dentro de la secuencia.  
  
-   Una secuencia puede contener secuencias secundarias y puede repetir una subsecuencia dentro de una secuencia.  
  
-   Puede usar un campo en varios tipos de mensaje.  
  
-   Dentro de un campo, puede haber elementos o subcampos. Un elemento o un subcampo puede ser comunes a varios campos.  
  
-   Cada secuencia repetida se representa mediante un nodo de grupo.  
  
-   Cada campo Sí habrá varios niveles nodal, cada uno de ellos se describe como un registro.  
  
-   Un elemento de esquema representa sólo el subcampo de nivel más bajo.  
  
-   Registros y elementos comunes se definen en el esquema de base y comunes, tal y como se describe a continuación.  
  
-   Algunos campos se pueden representar en varios formatos (como campos de entidad). Estos campos se definen como campos de elección en el esquema.  
  
 Algunos campos tienen una limitada a conjuntos de valores. En su mayor parte, el esquema muestra estos valores. Definiciones de esquema también incluyen la validación del juego de caracteres.