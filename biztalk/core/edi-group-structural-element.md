---
title: Elemento estructural de EDI grupo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 100a7118-9c02-474e-8685-9e4bb6f52e81
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555d7b86e069adda4f7761b698793fd4ec2af721
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="edi-group-structural-element"></a>Elemento estructural de grupo EDI
El grupo contiene uno o más conjuntos de transacciones. Un grupo de EDIFACT debe contener conjuntos de transacciones del mismo tipo. Un grupo de X12 puede contener conjuntos de transacciones de tipo similar (en función de la asignación de conjunto de transacciones - grupo (GS01-ST01)) o conjuntos de transacciones del mismo tipo. La tabla siguiente conjuntos de transacciones de listas X12 similar (ST01), que pueden incluirse en un único grupo (GS01).  
  
|GS01|ST01|  
|----------|----------|  
|CF|844|  
|CF|849|  
|DX|894|  
|DX|895|  
|FR|821|  
|FR|827|  
|GC|920|  
|GC|924|  
|GC|925|  
|GC|926|  
|HC|837|  
|HC|837_D|  
|HC|837_I|  
|HC|837_P|  
|IA|110|  
|IA|980|  
|E/S|310|  
|E/S|312|  
|ME|198|  
|ME|200|  
|ME|201|  
|ME|245|  
|ME|261|  
|ME|262|  
|ME|263|  
|ME|833|  
|ME|872|  
|MG|203|  
|MG|206|  
|MG|259|  
|MG|260|  
|MG|264|  
|MG|266|  
|OG|875|  
|OG|876|  
|PK|196|  
|PK|839|  
|QG|878|  
|QG|879|  
|QG|888|  
|QG|889|  
|QG|896|  
|QO|313|  
|QO|315|  
|RO|300|  
|RO|301|  
|RO|303|  
|RQ|836|  
|RQ|840|  
|RS|869|  
|RS|870|  
|SL|135|  
|SL|139|  
|SO|302|  
|SO|311|  
|SO|317|  
|SO|319|  
|SO|322|  
|SO|323|  
|SO|324|  
|SO|325|  
|SO|326|  
|SO|361|  
|TO|197|  
|TO|199|  
|TO|265|  
|TO|485|  
|TO|486|  
|TP|460|  
|TP|463|  
|TP|466|  
|TP|468|  
|TP|490|  
|TP|492|  
|TP|494|  
|WA|140|  
|WA|141|  
|WA|142|  
|WA|143|  
  
> [!NOTE]
>  Un grupo de HIPAA 5010 también permite incluir conjuntos de transacciones de diferentes versiones en un único grupo.  
  
 Si aparece una excepción al procesar un conjunto de transacciones, las propiedades de la entidad EDI se usan para determinar si se suspende todo el intercambio o solo el conjunto de transacciones en el que se produce el error.  
  
 Un grupo debe comenzar con un encabezado de grupo funcional (GS en X12 o UNG en EDIFACT) y finalizar con un finalizador de grupo funcional (Ge en X12 o UNE en EDIFACT). El encabezado de grupo contiene los códigos del remitente y el receptor, la fecha y la hora, un número control que hace coincidir el encabezado con el finalizador, un identificador de grupo que define la colección de conjuntos de transacciones que deben incluirse dentro del grupo funcional y otra información. El finalizador de grupo tiene un elemento que indica el número de conjuntos de transacciones dentro del grupo.  
  
 Un grupo es opcional en un intercambio EDIFACT. Un intercambio EDIFACT puede contener varios conjuntos de transacciones incluso si no hay presente ningún grupo (el segmento UNG no está presente). En este caso, los conjuntos de transacciones deben ser todos del mismo tipo y los conjuntos de transacciones en un único grupo deben ser también del mismo tipo. Por ejemplo, los conjuntos de transacciones APERAK y ORDERS no pueden estar presentes en un único grupo o en un intercambio que no tenga varios grupos.  
  
 Un grupo es necesario en un intercambio X12.